# Transaction-Tracking

To enable 8select-CSE sales tracking you have to integrate a second JavaScript code snippet. The sales tracking has to be implemented on the page that is displayed after a successful checkout.

The code snippet needs to be placed in the HTML anywhere after the code of the 8select-CSE JavaScript-SDK.

**WARNING** - Prices have to be defined in cents - so `199,95 €` has to be defined as `19995`.

```javascript
<script type="text/javascript">
  window.eightlytics(
    'purchase',
      {
        customerid: '1234',
        orderid: '1234',
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
  );
</script>
```

## API

### eightlytics\('purchase', order\)

**order**

| field | type | required | description |
| :--- | :--- | :--- | :--- |
| customerid | string | required | unique customer identifier |
| orderid | string | required | unique transaction identifier |
| products | array of product | required | which products does the order contain |

**product**

| field | type | required | description |
| :--- | :--- | :--- | :--- |
| sku | string | required | product identifier |
| amount | integer | required | how many units are added to the cart |
| price | integer | required | what does one unit cost in _**euro cent**_ |

```javascript
{
  customerid: '1234',
  orderid: '1234',
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

