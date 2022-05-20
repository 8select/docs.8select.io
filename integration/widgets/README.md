---
description: UI elements for web
---

# Widgets

Content is displayed in the shop with the help of various widgets. The widgets are simple HTML elements and are filled with content by our 8.SDK Web.\
The widgets are configured via `data` attributes. There are static and dynamic attributes.

{% hint style="info" %}
The 8SELECT integration team will adjust the widget styling 🎨 to your shop design. ❤️&#x20;
{% endhint %}

### Example 8.SET Compose

The widget is used to display cross-selling content in the form of product sets for a product.

```markup
<div data-8select-widget-id="8.SET-Compose" data-sku="42"></div>
```

{% hint style="info" %}
You can find a detailed description in the [**WIDGETS**](https://docs.8select.io/widgets/) section.
{% endhint %}

### Static Attributes

The value of these attributes does not change, for example`data-8select-widget-id`.

### Dynamic Attributes

The value of these attributes can change, for example `data-sku`. Depending on the product, a different value will be used here.

### Adding widget elements after 8.SDK was added

If you add 8SELECT widgets asynchronous the 8.SDK has to be informed about new widgets via its API.

```javascript
// failsafe if the 8.SDK is not yet injected
if (typeof _8select === "undefined") {
  return
}
// scan DOM for 8SELECT widgets and fill with content
_8select.initCSE();
```
