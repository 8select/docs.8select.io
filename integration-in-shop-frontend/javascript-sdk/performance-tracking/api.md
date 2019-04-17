# API

## Auftrag übermitteln

`eightlytics('purchase', order)`

{% tabs %}
{% tab title="order" %}
| field | type | required | description |
| :--- | :--- | :--- | :--- |
| `customerid` | string | required | unique customer identifier |
| `orderid` | string | required | unique transaction identifier |
| `products` | array of **`product`** | required | products of order |
{% endtab %}

{% tab title="product" %}
| field | type | required | description |
| :--- | :--- | :--- | :--- |
| `sku` | string | required | product identifier |
| `amount` | integer | required | how many units are added to the cart |
| `price` | integer | required | what does one unit cost in _**euro cent**_ |
{% endtab %}
{% endtabs %}

### Beispiel

```javascript
{
  customerid: '1234-anonymous',
  orderid: 'O-2019-01-1234',
  products: [
    {
      sku: '12345',
      amount: 3,
      price: 1199
    },
    {
      sku: '456',
      amount: 1,
      price: 19995
    }
  ]
}
```

