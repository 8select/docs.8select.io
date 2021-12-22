# Event Validation

Incoming analytics events are validated before they are accepted and processed. If you encounter any errors during the integration of 8.API Tracking in your product, you can check the structure of your events against our validation test endpoint at `https://api.8select.io/analytics/v3/events/validate`:

```bash
POST /analytics/v3/events/validate
Host: https://api.8select.io
Content-Type: application/json
x-api-id: <Your API ID>

{
  "type": "view",
  "view": {
    "type": "setCompose"
  },
  "context": [
    {
      "type": "user",
      "user": {
        "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
      }
    }
  ]
}
```

The above event is missing the `setCompose` property, which is required for `view` events of type `"setCompose"`. The validation endpoint will thus among others report this violation:

```javascript
[
  ...,
  {
    "instancePath": "/view",
    "schemaPath": "#/definitions/PayloadSetCompose/required",
    "keyword": "required",
    "params": {
      "missingProperty": "setCompose"
    },
    "message": "must have required property 'setCompose'"
  },
  ...
]
```

{% hint style="warning" %}
Please note, that the validation endpoint is currently set to be very verbose. This means, it will often contain multiple alerts caused by the same schema violation. We are working on a solution to make the output more concise.
{% endhint %}
