# view

A view event should be triggered whenever a piece of content slides into the users viewport. Assuming that you are showing 8.SET Compose product set data, that event should look like the following example.

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

The `userId` must be a consistent identifier as described in the [user identification](../../general/user-identification.md) section. Context should currently always contain a single object `{ "type": "api" }`.

### type

The type is `view` with an additional property named `view`. The view property will contain

