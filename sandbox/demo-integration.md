# Demo-Integration

To test the integration, the 8.SDK can be inserted into the shop via the (Chrome) Developer Tools. For this purpose, there is a demo tenant as well as demo product data and content.&#x20;

Insert and execute the following snippets one by one to show the widget 8.SET Compose at the top of the current page.

### Add 8.SDK Web in demo mode to your shop

```javascript
// Load 8.SDK

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

### Add a widget to your shop

You can add any widget via its id like described in the section [WIDGETS](https://docs.8select.io/widgets/).

```javascript
// Add 8.SET Compose Widget
_8select.demo('8.SET-Compose')
```

{% hint style="warning" %}
Currently only the widget `8.SET-Compose` supports the demo mode.
{% endhint %}
