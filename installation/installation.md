# Installation

Das 8select-CSE JavaScript SDK bietet alle clientseitigen Funktionen um die 8select-CSE vollständig in eine Webseite einzubinden.

Es ermöglicht die Nutzung des:

* SYS-PSV Widget - um ein Produktset für eine SKU anzuzeigen
* SYS-PSV Button - um einen Button mit dem Hinweis auf ein passendes Produktset anzuzeigen
* SYS-ACC Widget - um ergänzende Vorschläge zu einer in den Warenkorb gelegten SKU anzuzeigen
* PSP-PSV Widget - um ein bestimmtes Produktsets anzuzeigen
* PSP-TLV Widget - um eine Liste von Produktsets anzuzeigen
* ELTX-Client - für das CSE Performance-Tracking

Das SDK und die Widgets funktionieren in Desktop- und mobilen Webrowsern.

## API-ID

In vielen Code-Snippets befindet sich der Wert `<API-ID>`. Dieser muss durch `API-ID` ersetzt werden, die 8select zur Verfügung stellt.

## Wie wird die 8select-CSE integriert?

Die 8select-CSE wird mit Hilfe des JavaScript SDK muss nicht heruntergeladen werden. Es wird einfach über ein JavaScript-Codeausschnitt auf der Webseite im HTML platziert.

Das SDK wird asynchron geladen ohne Ladevorgänge von anderen Elementen auf der Webseite zu blockieren.

Mit Hilfe von folgendem Codeausschnitt wird das SDK geladen:

```javascript
<script type="text/javascript">
    (function(d, s, w) {
      var apiId = '<API-ID>';

      window.eightlytics || function (w) {
          w.eightlytics = function () {
            window.eightlytics.queue = window.eightlytics.queue || []
            window.eightlytics.queue.push(arguments)
          };
      }(w);
      var script = d.createElement(s);
      script.src   = 'https://wgt.8select.io/' + apiId + '/loader.js';
      var entry = d.getElementsByTagName(s)[0];
      entry.parentNode.insertBefore(script, entry);
    })(document, 'script', window);
</script>
```

## Funktionsweise des 8select-CSE JavaScript SDK

Das Widget-Loader Script `loader.js` ist eine ca. 5 KB große JavaScript Datei. Dieses Script erzeugt ein FIF \(Friendly IFrame\) in dem die 8select CSE geladen wird.

Diese Technik verhindert das Blockieren von Downloads anderer Ressourcen. Außerdem wird das `onload` Event des Browsers nicht blockiert. Somit beeinflusst das Einbinden der 8select CSE in keinster Weise die Ladezeiten Ihres Shops.

Nachdem das 8select-CSE JavaScript SDK geladen ist, füllt dieses automatisch alle gekennzeichneten div-Elemente mit den entsprechenden Widgets.

