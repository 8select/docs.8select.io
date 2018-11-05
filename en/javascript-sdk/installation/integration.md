# Integration

## API-ID

In many code snippets the value `<API-ID>` occurs. Replace all occurrences with the `API-ID` which 8select has provided. 

## How to integrate the 8select-CSE?

The 8select-CSE is integrated by the JavaScript SDK and doesn't need to be downloaded. A JavaScript code snippet simply needs to be placed in the HTML of the website.

The SDK is loaded asynchronously without blocking the loading processes of any other element of the site.

You can load the SDK with this code snippet:

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

