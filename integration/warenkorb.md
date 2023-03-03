---
description: Allow to add products to your cart from within 8SELECT widgets
---

# Shopping Cart

Many widgets allow a product to be added directly to the shopping cart.

Widgets that allow to add products to the cart will call the function `_eightselect_shop_plugin.addToCart()`. This function can then directly contain the code to add something to the shopping cart or call another function that is already implemented in the shop frontend.

{% hint style="warning" %}
To identify a product variant that should be added to the cart we currently only have the **sku** available. For **sku**, the same value as in the [product export](../product-export/base-data/details.md#sku-sku) is used.
{% endhint %}

```javascript
// 8.SDK Web configuration for shop's cart API
<script type="text/javascript">
  window._eightselect_shop_plugin = window._eightselect_shop_plugin || {};
  window._eightselect_shop_plugin.addToCart = function (sku, quantity, Promise) {
    // the function has to return a promise
    // you can use the injected Promise or use your own polyfill
    
    // add your cart logic here
    // this is just an example - shopApi is something you actually have to implement
    return new Promise(function(resolve, reject) {
      var response = shopApi.add2cart(sku);
      if (response === "OK") {        
        return resolve("done");
      }

      return reject(new Error("add2cart failed"));
    }
  }
</script>

// 8.SDK Web
<script type="text/javascript">
    ...
</script>
```

{% hint style="info" %}
The script is needed on all pages where widgets are used.
{% endhint %}

{% hint style="success" %}
A `Promise` object is injected into the function. A polyfill is provided for older browsers. This means that this does not have to be covered by the shop.
{% endhint %}

[\
](https://app.gitbook.com/@8select/s/docs/\~/drafts/-MRQJtvn2WI5oMAsvGIj/integration/warenkorb)

