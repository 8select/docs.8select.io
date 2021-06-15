# User views 8.SET Compose content

Let's assume you are showing content from 8.SET Compose that was loaded via [8.API](../../../api/8.set-compose/). Whenever a user visits that page and sees that content you should send the respective `view` event. Please ensure this event to be triggered only once per page view for a given set and only once the content is at least 50% in the device's viewport.

Suppose, 8.API returned a payload like this:

```javascript
{
  "data": {
    "setCompose": { // currently named productSets but will be renamed
      "edges": [
        {
          "node": {
            "id": "f0db275c-f7ef-4a2c-8704-f51318c261ba",
            "title": "Steppjacke mit rosa Pullover und dunkelblauer Jeanshose",            
            "setProducts": [
              ...
            ]
          }
        }
      ]
    }
  }
}          
```

The event you send would look like that:

```javascript
{ 
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "view",

	"view": {
		"type": "setCompose",
		"setCompose": {
			"id": "f0db275c-f7ef-4a2c-8704-f51318c261ba",
		},
	},

	"context": [
		{ "type": "api" }
	]
}
```

The type of the event is `view`. The corresponding `view` property is intended to specify the target of the event. In our case, this would be `setCompose` as that is the type of data we requested from the API. Again, to describe the target more specifically, we include the `id` of the presented product set — as returned in the API response — in a `setCompose` property.

Lastly, the `context` must contain a single object  `{ "type": "api" }` as described in the [context](../../general/context.md) section.

