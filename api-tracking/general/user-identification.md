# User Identification

To enable user-based metrics the user has to be identified with a consistent identifier. The identifier is wrapped in a context object and must be consistent for all events concerning a single user:

```javascript
{
  ...,
  "context": [
    {
      "type": "user",
      "user": {
        "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67" // uuid-v4
      }
    }
  ],	
  ...
}
```

The identifier should be anonymized, i.e. a generated id without any connection to personal data.\
This has to be done on a best efforts basis. We know that making this work 100% of the time is impossible because users can clear their device cache or change devices or something else to break the consistency.

{% hint style="info" %}
**User-based metrics** are metrics that actually require to tie an event stream to a certain user.&#x20;

One example is the metric about order lines that are generated through 8SELECT content.&#x20;

To know that specific products where bought because a user interacted with that product via the 8SELECT content all those events need to be tied to that specific user, i.e. need a user id in the context. Otherwise it is not possible to match order events with view or interact events.
{% endhint %}
