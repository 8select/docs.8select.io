# Shopping cart interface

To enable customers to add a product from the widget to their shopping cart, the shopping cart needs to be accessible through JavaScript.

To achieve this, a JavaScript function `_eightselect_shop_plugin` needs to be defined within the global namespace:

```javascript
window._eightselect_shop_plugin = window._eightselect_shop_plugin || {}
window._eightselect_shop_plugin.addToCart = function (sku, quantity, Promise) {
  try {
    //add your custom code to add sku to cart here
    return Promise.resolve()
  } catch (error) {
    return Promise.reject(error)
  }
}
```



