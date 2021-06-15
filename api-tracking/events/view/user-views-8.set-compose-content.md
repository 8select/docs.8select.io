# User views 8.SET Compose content

Let's assume you are showing content from 8.SET Compose that was loaded via [8.API](../../../api/8.set-compose/). Whenever a user visits that page and sees that content you should send the respective `view` event. Please ensure this event to be triggered only once per page view for a given set and only once the content is at least 50% in the device's viewport.

&lt;nice gif here&gt;

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
            "description": null,
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
			"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
		},
	},

	"context": [
		{ "type": "api" }
	]
}
```

* the type is view
* the type of the view is setCompose
* setCompose content is id from api

