# API

## initCSE\(\)

If your shop reloads the widget HTML elements asynchronously \(eg Shopware shopping worlds \), the CSE has to be informed afterwards. This is done by calling `initCSE()`


```javascript
window._8select.initCSE();
```

## reinitSys\(newSku, \[oldSku\]\)

If your shop reloads product variants via Ajax, you have to inform the SYS-PSV widget about the changed SKU.

```javascript
window._8select.reinitSys("21");
```

If the current SKU is known, you can pass it as the 2nd parameter. This helps the CSE find the right widget, if there are more widgets on the same page.

```javascript
window._8select.reinitSys("21", "42");
```

