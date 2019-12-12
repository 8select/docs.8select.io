# SDK Snippet

Mit Hilfe von folgendem Codeausschnitt wird das SDK geladen.

{% code title="" %}
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
{% endcode %}



