# JavaScript SDK

Um Content im Shop auszuspielen muss das JavaScript SDK eingebunden sein. Die Variable `apiId` muss mit der von uns bereitgestellten API-ID belegt werden.

```javascript
<script type="text/javascript">
    (function(d, s, w) {
      var apiId = '<API-ID>';
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
</script>
```

{% hint style="warning" %}
Das Script sollte soweit oben wie möglich im `<head>` stehen, damit es so früh wie möglich ausgeführt wird.  
Da das Script dynamisch eingefügt wird, ist es `async` und das Laden der Seite wird nicht geblockt. Mehr dazu [hier](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement#Dynamically_importing_scripts).
{% endhint %}

{% hint style="info" %}
Das Script wird auf allen Seiten benötigt auf denen Widgets genutzt werden.   
Für das Transaktions-Tracking muss es auch auf der Seite nach dem Checkout eingebunden werden.
{% endhint %}



