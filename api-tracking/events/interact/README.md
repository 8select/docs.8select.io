# interact

An interact event should be triggered whenever a piece of content is interacted with by a user. Assuming that you are showing 8.SET Compose product set data and a user clicks on a product contained in that set, the event should look like the following example:

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
	    "type": "setCompose",
	    "setCompose": {
	      "id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388"
	    }
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

The `userId` must be a consistent identifier as described in the [user identification](../../general/user-identification.md) section. The `context` should currently always contain object `{ "type": "api" }` and the information about the containing product set as defined in the [context](../../general/context.md) section.

An interact event is identified by its type `interact` and an additional `interact` property containing specific information about the content being interacted with. This property should in turn have a type and content-specific payload, as well as an optional third property `action` specifying the user interaction, e.g. `click` or `addToCart`.

{% hint style="info" %}
Currently, only `product` interactions are taken into consideration.
{% endhint %}

## product

An interact event with type `product` must contain a `product` property containing the `sku` of the respective product and can contain an `action`.

Some example actions: `click`, `addToCart`, `navigateTo`, `addToWishlist`, `like`, `share`.

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

While an arbitrary `action` can be supplied we currently only have KPIs that differentiate between `addToCart` and any other action. 

{% hint style="info" %}
If you are not sure how to name the `action` simply omit the property.
{% endhint %}

