<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
[Übersicht](https://docs.8select.io/CSE-integration-manual/)

- [JavaScript-SDK API](#javascript-sdk-api)
  - [initCSE()](#initcse)
  - [reinitSys(newSku, [oldSku])](#reinitsysnewsku-oldsku)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# JavaScript-SDK API

## initCSE()

Wenn ihr Shop die Widget HTML-Elemente Asynchron nachläd (z.B. Shopware Einkaufswelten), dann muss nach dem Laden die CSE darüber informiert werden. Dies erfolgt durch einen Aufruf von `initCSE()`

```javascript
window._8select.initCSE();
```

## reinitSys(newSku, [oldSku])

Wenn Ihr Shop Varianten via Ajax nachlädt, so müssen Sie das SYS-PSV Widget über die geänderte SKU informieren.

```javascript
window._8select.reinitSys("21", "42");
```
