---
description: 8.SDK Web
---

# 8.SDK Web \(JavaScript SDK\)

In order to display content in the shop, the **8.SDK Web** \(JavaScript SDK\) must be integrated. The variable `apiId` must be filled with the API ID provided by us.

```javascript
<script type="text/javascript">
    (function(d, s, w) {
      var apiId = '<API-ID>';
      w.eightlytics || function (w) {
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
The script should be placed as far up as possible in the DOM, preferably as first in the `<head>` tag to ensure it is executed as early as possible. Since the script is inserted dynamically, it is `async` by default and the loading of the page is not blocked. More about this [here](https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement#dynamically_importing_scripts).
{% endhint %}

{% hint style="info" %}
The script is required on all pages where 8SELECT widgets are used.  
For transaction tracking, it must also be included on the page **after checkout** where the tracking can happen.
{% endhint %}



