<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [8select-CSE Widgets](#8select-cse-widgets)
  - [SYS-PSV Widget - ein Produktset für eine SKU anzeigen](#sys-psv-widget---ein-produktset-f%C3%BCr-eine-sku-anzeigen)
    - [SYS-PSV Widget mit anderer SKU neuladen](#sys-psv-widget-mit-anderer-sku-neuladen)
    - [SYS-PSV Callback](#sys-psv-callback)
  - [SYS-PSV Button - ein Button mit dem Hinweis auf ein passendes Produktset anzeigen](#sys-psv-button---ein-button-mit-dem-hinweis-auf-ein-passendes-produktset-anzeigen)
  - [SYS-ACC Widget - ergänzende Vorschläge zu einer in den Warenkorb gelegten SKU anzeigen](#sys-acc-widget---erg%C3%A4nzende-vorschl%C3%A4ge-zu-einer-in-den-warenkorb-gelegten-sku-anzeigen)
    - [Widget-Element](#widget-element)
      - [Parameter](#parameter)
      - [CSS Klassen](#css-klassen)
      - [Beispiel Antwort vom Endpunkt](#beispiel-antwort-vom-endpunkt)
      - [Widget-Element initialisieren, falls das Widget nachträglich ins DOM geschrieben wird](#widget-element-initialisieren-falls-das-widget-nachtr%C3%A4glich-ins-dom-geschrieben-wird)
    - [SYS-ACC Callback](#sys-acc-callback)
  - [PSP-PSV Widget - ein bestimmtes Produktsets anzeigen](#psp-psv-widget---ein-bestimmtes-produktsets-anzeigen)
  - [PSP-TLV Widget - eine Liste von Produktsets anzeigen](#psp-tlv-widget---eine-liste-von-produktsets-anzeigen)
  - [Callbacks](#callbacks)
  - [Lazy Loading](#lazy-loading)
  - [Container-Elemente / Überschriften / Erweiterungen](#container-elemente--%C3%BCberschriften--erweiterungen)
      - [Beispiel mit Container-Element](#beispiel-mit-container-element)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# 8select-CSE Widgets

Den folgenden Codeausschnitt an der Stelle einbinden, an der das entsprechende Widget angezeigt werden soll.

## SYS-PSV Widget - ein Produktset für eine SKU anzeigen

```html
<div data-8select-widget-id="sys-psv" data-sku="42"></div>
```

`data-sku` ist die SKU des aktuellen Artikels. Die CSE sucht basierend darauf ein Produktset welches diesen Artikel enthält.
Der Wert für `data-sku` muss dynamisch gesetzt werden und muss einer der im Stammdatenfeed übergebenen SKU oder Master-SKU entsprechen.

### SYS-PSV Widget mit anderer SKU neuladen

Wenn Ihr Shop Varianten via Ajax nachlädt, so müssen Sie das SYS-PSV Widget über die geänderte SKU informieren.

```javascript
window._8select.reinitSys("<neue-sku>", "<alte-sku>");
```

### SYS-PSV Callback

Im Erfolgs- bzw. Fehlerfall wird `window._eightselect_config.sys.callback` aufgerufen sofern eine Funktion definiert ist.

**Beispiel**

```
window._eightselect_config = window._eightselect_config || {}
window._eightselect_config['sys'] = {
  callback: function (error, sku, widgetUuid) {
    if (error) {
      // something went wrong or no set was found for given sku
      return
    }
    // everything fine and a set was found for given sku
    // we can show a button that let's the customer know that we have a set and allows him/her to navigate to the widget with one click
    document.querySelector('[data-8select-widget-id=sys-psv-button]').style.display = 'block'
  }
}
```

## SYS-PSV Button - ein Button mit dem Hinweis auf ein passendes Produktset anzeigen

Der SYS-PSV-Button weißt den Nutzer der Webseite darauf hin, dass es zum aktuell angesehenen Artikel ein passendes Produktset gibt.  
Der Nutzer kann mit einem Klick auf den Button direkt zum Produktset runterscrollen oder springen.

Ein beliebiges Element mit dem Attribut `data-8select-widget-id="sys-psv-button"` wird als SYS-PSV Button erkannt. Dieses Element sollte initial versteckt sein. Durch die Definition eines Callbacks wird der Button eingeblendet, wenn ein Produktset zum Artikel verfügbar ist.

**Beispiel**

```
<button
    data-8select-widget-id="sys-psv-button"
    onclick="_8select.utils.goToWidget(document.querySelectorAll('[data-8select-widget-id=sys-psv]')[0].getAttribute('data-8select-widget-uuid'), 0);"
    ontouchend="_8select.utils.goToWidget(document.querySelectorAll('[data-8select-widget-id=sys-psv]')[0].getAttribute('data-8select-widget-uuid'), 0);"
    type="submit"
    style="display: none;"
  >Passender Look</button>
```

```
window._eightselect_config = window._eightselect_config || {}
window._eightselect_config['sys'] = {
  callback: function (error, sku, widgetUuid) {
    if (error) {
      // something went wrong or no set was found for given sku
      return
    }
    // everything fine and a set was found for given sku
    // we can show a button that let's the customer know that we have a set and allows him/her to navigate to the widget with one click
    document.querySelector('[data-8select-widget-id=sys-psv-button]').style.display = 'block'
  }
}
```

```
_8select.utils.goToWidget(widgetUuid, offset)
```

## SYS-ACC Widget - ergänzende Vorschläge zu einer in den Warenkorb gelegten SKU anzeigen

### Widget-Element

```html
<div data-8select-widget-id="sys-acc" data-sku="42" data-include-css="true"></div>
```

#### Parameter

`data-sku` ist die SKU des aktuellen Artikels. Die CSE sucht basierend darauf ein Produktset welches diesen Artikel enthält.
Der Wert für `data-sku` muss dynamisch gesetzt werden und muss eine der im Stammdatenfeed übergebenen SKU oder Master-SKU entsprechend.

`data-include-css` kann `true` oder `false` sein. Wird der Wert weggelassen, entspricht das dem Wert `false`.
Steht der Wert auf `true` so wird ein Basis CSS für ein CSS-Grid basierend auf https://purecss.io/grids/ ausgeliefert.
Außerdem werden CSS Deklarationen für einzelne Elemente ausgeliefert. Kommen neue Elemente hinzu werden diese z.B. über die Deklaration `display:none` ausgeblendet.

#### CSS Klassen

Folgende CSS Klassen sind nutzbar. Für manche Klassen sind Standardwerte gesetzt. Diese können mit Hilfe von `!important` überschrieben werden.

```CSS
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

#### Beispiel Antwort vom Endpunkt

Das HTML des zurückgelieferten Widgets hat folgende Struktur:

```html
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

#### Widget-Element initialisieren, falls das Widget nachträglich ins DOM geschrieben wird

Wie alle anderen Widgets wird auch das SYS-ACC Widget automatisch vom `widget-loader` erkannt, sofern es von vornherein im DOM ist.

Wird das Widget-Element erst nachträglich in das DOM aufgenommen, zum Beispiel durch ein Modal welches über einen AJAX Aufruf gefüllt wird, so muss das Widget-Element manuell initialisiert werden.

```
window._8select.initCSE();
```

### SYS-ACC Callback

Im Erfolgs- bzw. Fehlerfall wird `window._eightselect_config['sys-acc'].callback` aufgerufen sofern eine Funktion definiert ist.

**Beispiel**

```
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

## PSP-PSV Widget - ein bestimmtes Produktsets anzeigen

```html
<div data-8select-widget-id="psp-psv" data-set-id="65b1169b-12a7-46a2-a9c0-6561861cbca5"></div>
```

`data-set-id` definiert welches Produktset angezeigt werden soll. Den Wert für `data-set-id` entnehmen Sie bitte der Management-Console.

## PSP-TLV Widget - eine Liste von Produktsets anzeigen

```html
<div data-8select-widget-id="psp-tlv" data-tags="abiball,abendgarderobe"></div>
```

`data-tags` grenzt die angezeigten Produktsets auf bestimmte Tags ein. Die Tags entnehmen Sie bitte der Management-Console.

## Callbacks

Einige Widgets rufen einen Error-First-Callback bei Erfolg- bzw. Fehlerfall auf.
Darüber lässt sich beispielsweise alternativer Inhalt anstelle eines Widgets anzeigen, wenn zum Beispiel gerade kein Produktset für ein bestimmtes Produkt zur Verfügung steht.

## Lazy Loading

Um Widget-Elemente erst zu laden wenn diese im sichtbaren Bereich, oder in einem bestimmten Abstand zum sichtbaren Bereich sind, kann das Attribut `data-load-distance-factor` gesetzt werden.

`data-load-distance-factor` ist optional und kann eine Zahl größer oder gleich `0` sein. Der Wert beschreibt den Faktor, den ein Widget-Element vom unteren sichtbaren Bereich entfernt sein muss, bis es geladen wird. Siehe dazu folgende [Illustration](#file-wgt-ldr-lazy-load-pdf).

Ist das Attribut nicht gesetzt, so werden alle Widget-Elemente direkt geladen.

Der Wert `0` startet den Ladevorgang des Widgets sobald das Element den unteren sichtbaren Bereich erreicht.

Beim Wert `1` wird der Ladevorgang bereits einen Bildschirmabstand früher gestartet. Je größer der Wert, desto früher wird ein Widget geladen.

```html
<div data-sku="42" data-8select-widget-id="sys-psv" data-load-distance-factor="1"></div>
```

## Container-Elemente / Überschriften / Erweiterungen

Das Widget kann an beliebiger Stelle im HTML Dokument eingebunden werden.
Sie können das Widget also nahtlos in ihr Layout einfügen.

Die 8select Produktsets sind dynamisch, je nach Verfügbarkeit von Artikeln kann es also mehr oder weniger aktive Produktsets geben.
Um zu vermeiden, dass Container-Elemente allein stehen bleiben, wenn das spezifizierte Produktset mal nicht mehr Verfügbar ist, sollte das oberste Container-Element initial versteckt sein.
Das heißt die Eigenschaft `display` sollte den Wert `none` erhalten. Darüber hinaus **muss** die CSS-Klasse `-eightselect-widget-container` gesetzt sein.

Sobald das Widget sowie das Produktset geladen sind, wird das Container-Element bzw. das Widget eingeblendet.

#### Beispiel mit Container-Element

```html
<div class="teaserBox -eightselect-widget-container" style="display: none;">
    <h3 class="teaserTitle">Look der Woche</h3>
    <div class="teaserWrapper">
        <div data-8select-widget-id="psp-psv" data-set-id="365"></div>
    </div>
</div>
```
