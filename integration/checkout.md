---
description: Transfer order data for analytics and performance based pricing
---

# Checkout

The commission is based on performance, i.e. only products purchased via our widgets are eligible for commission. To determine these products, the purchases in the shop are compared with the interactions in our widgets. For this purpose, all shop transactions must be transmitted. The transmission takes place without personal data and only contains the individual order items.

{% hint style="warning" %}
For **`price`**, the price in cents per item must be transferred as an **`integer`**.  
For an item that costs 199.95 €, the value `19995` must be transferred. 

For **sku**, the same value as in the product export must be used. The value must be transmitted as a **string**.
{% endhint %}

```javascript
<script type="text/javascript">
    (function(d, s, w) {
      var apiId = '<API-ID>';
      w.eightlytics || function (w) {
          w.eightlytics = function () {
            window.eightlytics.queue = window.eightlytics.queue || [];
            window.eightlytics.queue.push(arguments);
          };
      }(w);
      var script = d.createElement(s);
      script.src   = 'https://wgt.8select.io/' + apiId + '/loader.js';
      var entry = d.getElementsByTagName(s)[0];
      entry.parentNode.insertBefore(script, entry);
    })(document, 'script', window);
</script>

// Two script tags, because the 8.SDK Web code has to run first to initialize the 8.LYTICS client

<script type="text/javascript">
  window.eightlytics(
    'purchase',
      {
        customerid: 'anonymous', // string
        orderid: '1234', // string
        products: [
          {
            sku: '12345', // string
            amount: 3, // integer
            price: 1199 // integer - price of 1 item in cent
          },
          {
            sku: '456', // string
            amount: 1, // integer
            price: 19995 // integer
          }
        ]
    }  
  );
</script>
```

{% hint style="info" %}
The **customerid** will be used to optimize content in the future. For the sake of simplicity and GDPR concerns we are removing it for now as a requirement. In the meantime just transfer `anonymous` as value.
{% endhint %}

{% hint style="info" %}
The **orderid** is used to compare our analytics data with the shop's analytics data on request. For example, for spot checks. If this is desired, the orderid must not be transmitted anonymously.
{% endhint %}

