# SYS-ACC Widget

## Widget-Element

```markup
<div data-8select-widget-id="sys-acc" data-sku="42" data-include-css="true"></div>
```

**Parameter**

`data-sku` ist die SKU des aktuellen Artikels. Die CSE sucht basierend darauf ein Produktset welches diesen Artikel enthält. Der Wert für `data-sku` muss dynamisch gesetzt werden und muss eine der im Stammdatenfeed übergebenen SKU oder Master-SKU entsprechend.

`data-include-css` kann `true` oder `false` sein. Wird der Wert weggelassen, entspricht das dem Wert `false`. Steht der Wert auf `true` so wird ein Basis CSS für ein CSS-Grid basierend auf [https://purecss.io/grids/](https://purecss.io/grids/) ausgeliefert. Außerdem werden CSS Deklarationen für einzelne Elemente ausgeliefert. Kommen neue Elemente hinzu werden diese z.B. über die Deklaration `display:none` ausgeblendet.

**CSS Klassen**

Folgende CSS Klassen sind nutzbar. Für manche Klassen sind Standardwerte gesetzt. Diese können mit Hilfe von `!important` überschrieben werden.

```css
.-eightselect-item-list {
}

.-eightselect-item {
}

.-eightselect-item-image {
}

.-eightselect-item-body {
}

.-eightselect-item-brand {
}

.-eightselect-item-name {
  display: none;
}

.-eightselect-item-sales-price {
}

.-eightselect-item-stroke-price {
}
```

**Beispiel Antwort vom Endpunkt**

Das HTML des zurückgelieferten Widgets hat folgende Struktur:

```markup
<div class="-eightselect-item-list -eightselect-g">
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
</div>
```

**Widget-Element initialisieren, falls das Widget nachträglich ins DOM geschrieben wird**

Wie alle anderen Widgets wird auch das SYS-ACC Widget automatisch vom `widget-loader` erkannt, sofern es von vornherein im DOM ist.

Wird das Widget-Element erst nachträglich in das DOM aufgenommen, zum Beispiel durch ein Modal welches über einen AJAX Aufruf gefüllt wird, so muss das Widget-Element manuell initialisiert werden.

```text
window._8select.initCSE();
```

## SYS-ACC Callback

Im Erfolgs- bzw. Fehlerfall wird `window._eightselect_config['sys-acc'].callback` aufgerufen sofern eine Funktion definiert ist.

**Beispiel**

```text
window._eightselect_config = window._eightselect_config || {}
window._eightselect_config['sys-acc'] = {
  callback: function (error, sku, widgetUuid) {
    if (error) {
      // something went wrong or no set was found for given sku
      alert('uh oh')
      return
    }
    // everything fine and a set was found for given sku
    alert('YEAH BABY!')

  }
}
```
