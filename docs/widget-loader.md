# README

[Übersicht](https://docs.8select.io/CSE-integration-manual/)

* [JavaScript-SDK API](widget-loader.md#javascript-sdk-api)
  * [initCSE\(\)](widget-loader.md#initcse)
  * [reinitSys\(newSku, \[oldSku\]\)](widget-loader.md#reinitsysnewsku-oldsku)

## JavaScript-SDK API

### initCSE\(\)

Wenn ihr Shop die Widget HTML-Elemente Asynchron nachläd \(z.B. Shopware Einkaufswelten\), dann muss nach dem Laden die CSE darüber informiert werden. Dies erfolgt durch einen Aufruf von `initCSE()`

```javascript
window._8select.initCSE();
```

### reinitSys\(newSku, \[oldSku\]\)

Wenn Ihr Shop Varianten via Ajax nachlädt, so müssen Sie das SYS-PSV Widget über die geänderte SKU informieren.

```javascript
window._8select.reinitSys("21", "42");
```

