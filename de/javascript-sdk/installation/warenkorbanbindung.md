# warenkorbanbindung

Damit Kunden Artikel aus den 8select Widgets heraus in den Warenkorb legen können, muss der Warenkorb via JavaScript zugänglich sein.

Dafür muss eine JavaScript Funktion `_eightselect_shop_plugin` im globalen Namespace definiert werden:

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



