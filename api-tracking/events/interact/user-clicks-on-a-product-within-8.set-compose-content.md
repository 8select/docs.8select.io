# User clicks on a product within 8.SET Compose content

Let's assume you are showing content from 8.SET Compose that was loaded via [8.API](../../../api/8.set-compose/). Whenever a user clicks on a product within that content you should send the respective `interact` event.

![](../../../.gitbook/assets/interactproduct.gif)

Suppose, 8.API returned a payload like this:

```javascript
{
  "data": {
    "setCompose": { // currently named productSets but will be renamed
      "edges": [
        {
          "node": {
            "id": "f0db275c-f7ef-4a2c-8704-f51318c261ba",
            "setProducts": [
              ...
              {
                "sku": "654321-7890"
              }
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
	"type": "interact",

	"interact": {
	  "action": "click",
		"type": "product",
		"product": {
			"sku": "654321-7890",
		},
	},

	"context": [
	  {
	    "content": {
			  "setCompose": {
				  "id": "f0db275c-f7ef-4a2c-8704-f51318c261ba",
			  },
			  "type": "setCompose",
			},
			"type": "content"
	  },
		{
		  "type": "user",
		  "user": {
		    "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
		  }
		}
	]
}
```

The type of the event is `interact`. The corresponding `interact` property is intended to specify the target and action of the event. In our case, this would be a `click` on a  `product`. Again, to describe the target more specifically, we include the `sku` of the product interacted with — as returned in the API response — in a `product` property.

Lastly, the `context` must contain an object with type `user` as described in the [context](../../general/context.md) section, as well as the `setCompose` context specifying the containing product set returned by the API as described in the [context](../../general/context.md) section.

