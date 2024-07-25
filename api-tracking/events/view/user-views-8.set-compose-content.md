# User views 8.SET content

Let's assume you are showing content from 8.SET that was loaded via [8.API](../../../api/examples/8.set.md). Whenever a user visits that page and sees that content you should send the respective `view` event. **Please ensure this event to be triggered only once per page view for a given set and only** [**once the content is at least 50% in the device's viewport or 50% of the content are in the viewport**](how-to-evaluate-if-view-event-can-be-sent.md)**.**&#x20;

![](../../../.gitbook/assets/viewContent.gif)

Suppose you requested content for product with SKU `457297-0001-00340`the event you send would look like this:

```javascript
{
  "type": "view",
  "view": {
    "type": "matchingProductClusters",
    "matchingProductClusters": {
      "id": "457297-0001-00340",
    }
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

The type of the event is `view`. The corresponding `view` property is intended to specify the target of the event. In our case, this would be `matchingProductClusters` as that is the type of data we requested from the API. Again, to describe the target more specifically, we include the `id` of the product we requested content for.

