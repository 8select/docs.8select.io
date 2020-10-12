# Warenkorbanbindung

Damit Kunden Artikel aus den 8select.CSE Widgets heraus in den Warenkorb des Shops legen können, muss der Warenkorb via JavaScript zugänglich sein.

Dafür muss eine JavaScript Funktion `_eightselect_shop_plugin.addToCart` im globalen Namespace definiert werden:

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

Widgets die eine Warenkorbfunktion beinhalten, zum Beispiel 8.SET Compose, greifen auf diese Funktion zu um Artikel in den Warenkorb zu legen. Die SKU wird also von Widget übergeben. Die SKU ist der Identifikator der auch im Produktexport als Identifikator für eine Variante genutzt wird.



