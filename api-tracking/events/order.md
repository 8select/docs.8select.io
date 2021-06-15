# order

## user orders products

* duplicate events will be filtered server side

```javascript
{
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "order",
	"order": {
		"id": "<any-order-id-string>",
		"lines": [
			"sku": "20624156",
			"grossPrice": {
				"amount": 4.95, // total price, i.e. item price * quantity
				"currency": "EUR" // currency code as defined by ISO 4217
			},
			"quantity": 5,
		]
	}
}
```

