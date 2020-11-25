# Demo-Integration

Um die Integration zu testen, kann das SDK über die \(Chrome\) Developer Tools im Shop eingefügt werden.  
Hierfür gibt es einen Demo Mandanten sowie Demo Produktdaten und Content.

Das folgende Snippet für das Widget 8.SET Compose ganz oben auf der aktuellen Seite ein.

```javascript
// 8.SET Compose Widget einfügen
sku = '8S-DEMO-Polohemd-M';
composeWidget = `<div data-sku="${sku}" data-8select-widget-id="sys-psv"></div>`;
composeHeadline = `<div>Passender Look</div>`
composeContainer = `<div class="-eightselect-widget-container" style="display: none;">${composeHeadline}${composeWidget}</div>`
composeSelector = `body`;
document.querySelector(composeSelector).insertAdjacentHTML('afterbegin', composeContainer);


// JavaScript SDK laden

(function(d, s, w) {
  var apiId = 'db54750f-80fc-4818-9455-30ca233225dc';
  window.eightlytics || function (w) {
      w.eightlytics = function () {
        window.eightlytics.queue = window.eightlytics.queue || [];
        window.eightlytics.queue.push(arguments);
      };
  }(w);
  var script = d.createElement(s);
  script.src   = 'https://wgt.8select.io/' + apiId + '/loader.js';
  var entry = d.getElementsByTagName(s)[0];
  entry.parentNode.insertBefore(script, entry);
})(document, 'script', window);
```

Durch die Anpassung von `composeSelector` und `afterbegin` kann das Widget an eine beliebige Stelle im Shop platziert werden.

{% hint style="info" %}
Im Demo-Modus funktioniert die Warenkorb Anbindung nicht - da die Demo-Artikel nicht im Shop verfügbar sind.
{% endhint %}



