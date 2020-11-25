# Warenkorb

Über viele Widgets kann ein Produkt direkt in den Warenkorb gelegt werden.

Widgets mit Warenkorb-Funktion rufen die Funktion `_eightselect_shop_plugin.addToCart()` auf. Diese Funktion kann dann direkt den Code beinhalten um etwas in den Warenkorb zu legen oder aber eine weitere Funktion aufrufen, die bereits vom Shop definiert ist.

```javascript
<script type="text/javascript">
  window._eightselect_shop_plugin = window._eightselect_shop_plugin || {};
  window._eightselect_shop_plugin.addToCart = function (sku, quantity, Promise) {
    try {
      //////
      //
      // Hier kommt der Code um etwas in den Warenkorb zu legen
      //
      //////
      return Promise.resolve();
    } catch (error) {
      return Promise.reject(error);
    }
  }
</script>
```

{% hint style="info" %}
Das Script wird auf allen Seiten benötigt auf denen Widgets genutzt werden. 
{% endhint %}

{% hint style="success" %}
In die Funktion wird ein `Promise` Objekt injiziert. Für ältere Browser wird ein Polyfill bereitgestellt. Somit muss dies nicht durch den Shop abgedeckt werden.
{% endhint %}

