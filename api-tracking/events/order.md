# order

An order event should be triggered whenever a user, i.e. one of your customers, places an order. It should look like the following example:

```javascript
{ 
	"userId": "c57a43f7-eefc-462b-b5a8-0ef421e90f67",

	"type": "order",

	"order": {
	  "id": "0987654321"
		"lines": [
		  {
			  "sku": "654321-7890",
			  "grossPrice": {
				  "amount": 0.99, // unit price
				  "currency": "EUR" // currency code as defined by ISO 4217
			  },
			  "quantity": 5
			},
			{
			  "sku": "567890-4321",
			  "grossPrice": {
				  "amount": 49.95,
				  "currency": "EUR"
			  },
			  "quantity": 1
			}
		]
	}
}
```

The `userId` must be a consistent identifier as described in the [user identification](../general/user-identification.md) section. Order events should not contain any [context](../general/context.md).

An order event is identified by its type `order` and an additional `order` property containing specific information about the products being ordered. This property must have the `id` of the order in your shop system and a `lines` property, containing a list of ordered items.

Each order lines entry must contain the `sku` of the ordered product and the quantity of items ordered of this product. Additionally, it must include a `grossPrice` object with a `currency` code, as defined by [ISO 4217](https://en.wikipedia.org/wiki/ISO_4217), and the `amount` of money paid \(including e.g. VAT\) for one unit of this entry, i.e. the price of a single item.

{% hint style="info" %}
Duplicate `order` events will be filtered server-side.
{% endhint %}



