# view

A view event should be triggered whenever a piece of content slides into the users viewport. Assuming that you are showing 8.SET Compose product set data, that event should look like the following example:

```javascript
{ 
	"type": "view",

	"view": {
		"type": "setCompose",
		"setCompose": {
			"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
		},
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

A view event is identified by it's type `view` and an additional `view` property containing specific information about the content being viewed. This property should in turn have a type and content-specific payload.

{% hint style="info" %}
Currently, only `setCompose` views are taken into consideration.
{% endhint %}

## setCompose

A view event with type `setCompose` must contain a `setCompose` property containing the `id` of the viewed product set:

```javascript
{ 
	...

	"view": {
		"type": "setCompose",
		"setCompose": {
			"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
		},
	},

	...
}
```



