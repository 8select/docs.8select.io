# Integration

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

