# interact

## user clicks on product

* can occur more than once per page view

```javascript
{
	"apiId": "bb3daa78-7195-4ed9-9220-c3bfae4d759d",
	"sessionId": "26250959-0b93-4b39-8b55-fa783e7c462b",
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "interact",

	"interact": {
		"action": "click", 
		"type": "product",
		"product": {
			"sku": "20624155"
		},
	},

	"context": [
		{
			"type": "setCompose",
			"setCompose": {
				"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
			},
		},
		{ "type": "api" }
	]
}
```

## user adds product to cart

* can occur more than once per page view

```javascript
{
	"apiId": "bb3daa78-7195-4ed9-9220-c3bfae4d759d",
	"sessionId": "26250959-0b93-4b39-8b55-fa783e7c462b",
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "interact",

	"interact": {
		"action": "addToCart", 
		"type": "product",
		"product": {
			"sku": "20624156"
		},
	},

	"context": [
		{
			"type": "setCompose",
			"setCompose": {
				"id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388",
			},
		},
		{ "type": "api" }
	]
}
```

