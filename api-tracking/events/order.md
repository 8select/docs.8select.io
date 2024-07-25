# order

An order event should be triggered whenever a user, i.e. one of your customers, places an order. It should look like the following example:

```javascript
{
  "type": "order",
  "order": {
    "id": "0987654321",
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

The context array must currently always contain an object with type `user` as defined in the [context](../general/context.md) section and the user ID specified therein must be a consistent identifier as described in the [user identification](../general/user-identification.md) section.&#x20;

An order event is identified by its type `order` and an additional `order` property containing specific information about the products being ordered. This property must have the `id` of the order in your shop system and a `lines` property, containing a list of ordered items.

Each order lines entry must contain the `sku` of the ordered product and the quantity of items ordered of this product. Additionally, it must include a `grossPrice` object with a `currency` code, as defined by [ISO 4217](https://en.wikipedia.org/wiki/ISO\_4217), and the `amount` of money paid (including e.g. VAT) for one unit of this entry, i.e. the price of a single item.

Lastly, the `context` must contain an object with type `user` as described in the [context](../general/context.md) section.

{% hint style="info" %}
Duplicate `order` events will be filtered on our server-side so you do not have to implement anything to solve that.
{% endhint %}

