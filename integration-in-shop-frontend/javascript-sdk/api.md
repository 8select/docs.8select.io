# API

## initCSE\(\)

Wenn ihr Shop die Widget HTML-Elemente Asynchron nachlädt \(z.B. Shopware Einkaufswelten\), dann muss nach dem Laden die CSE darüber informiert werden. Dies erfolgt durch einen Aufruf von `initCSE()`

```javascript
window._8select.initCSE();
```

## reinitSys\(newSku, \[oldSku\]\)

Wenn Ihr Shop Varianten via Ajax nachlädt, so müssen Sie das SYS-PSV Widget über die geänderte SKU informieren.

```javascript
window._8select.reinitSys("21");
```

Wenn die aktuelle SKU bekannt ist, kann diese als 2. Parameter übergeben werden. Das hilft der CSE das richtige Widget zu finden, sollte es mehrere Widgets auf der Seite geben.

```javascript
window._8select.reinitSys("21", "42");
```

