# interact

An interact event should be triggered whenever a piece of content is interacted with by a user. Assuming that you are showing 8.SET Compose product set data, and a user clicks on a product contained in that set, the event should look like the following example:

```javascript
{ 
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

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
	    "type": "setCompose",
	    "setCompose": {
	      "id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388"
	    }
	  },
		{ "type": "api" }
	]
}
```

The `userId` must be a consistent identifier as described in the [user identification](../../general/user-identification.md) section. The context should currently always contain object `{ "type": "api" }` and the information about the containing product set as defined in the [context](../../general/context.md) section.

An interact event is identified by it's type `interact` and an additional `interact` property containing specific information about the content being interacted with. This property should in turn have a type and content-specific payload, as well as a third property `action` specifying the user interaction, i.e. `click` or `addToCart`.

{% hint style="info" %}
Currently, only `product` interactions are taken into consideration.
{% endhint %}

## product

An interact event with type `product` must contain an `action`, as well as a `product` property containing the `sku` of the respective product. The `action` can currently either be `click` or `addToCart`.

```javascript
{ 
	...

	"interact": {
	  "action": "click",
		"type": "product",
		"product": {
			"sku": "654321-7890",
		},
	},

	...
}
```

