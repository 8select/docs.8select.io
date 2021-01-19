# Widgets

Mit Hilfe der verschiedenen Widgets wird Content im Shop ausgespielt. Die Widgets sind simple HTML Elemente und werden durch das JavaScript SDK mit Content befüllt.  
Über `data` Attribute werden die Widgets konfiguriert. Es gibt dabei statische und dynamische Attribute.

### Beispiel 8.SET Compose

Wird benutzt um Cross-Selling Content in Form von Product Sets für ein Produkt auszuspielen.

```markup
<div data-8select-widget-id="sys-psv" data-sku="42"></div>
```

{% hint style="info" %}
Im Abschnitt [**WIDGETS**](https://docs.8select.io/widgets) ist die Integration für alle verfügbaren Widgets detailliert beschrieben.
{% endhint %}

### Statische Attribute

Der Wert dieser Attribute ändert sich nicht, zum Beispiel `data-8select-widget-id`.

### Dynamische Attribute

Der Wert dieser Attribute kann sich ändern, zum Beispiel `data-sku` - je nach Produkt wird hier ein anderer Wert enthalten sein.



