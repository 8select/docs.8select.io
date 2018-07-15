# setup

[Übersicht](https://docs.8select.io/CSE-integration-manual/)

* [Installation](setup.md#installation)
  * [Wie wird die 8select-CSE integriert?](setup.md#wie-wird-die-8select-cse-integriert)
  * [API-ID](setup.md#api-id)

## Installation

Das 8select-CSE JavaScript SDK bietet alle clientseitigen Funktionen um die 8select-CSE vollständig in eine Webseite einzubinden.

Es ermöglicht die Nutzung des:

* SYS-PSV Widget - um ein Produktset für eine SKU anzuzeigen
* SYS-PSV Button - um einen Button mit dem Hinweis auf ein passendes Produktset anzuzeigen
* SYS-ACC Widget - um ergänzende Vorschläge zu einer in den Warenkorb gelegten SKU anzuzeigen
* PSP-PSV Widget - um ein bestimmtes Produktsets anzuzeigen
* PSP-TLV Widget - um eine Liste von Produktsets anzuzeigen
* ELTX-Client - für das CSE Performance-Tracking

Das SDK und die Widgets funktionieren in Desktop- und mobilen Webrowsern.

### Wie wird die 8select-CSE integriert?

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

### API-ID

In vielen Code-Snippets befindet sich der Wert `<API-ID>`. Dieser muss durch `API-ID` ersetzt werden, die 8select zur Verfügung stellt.

