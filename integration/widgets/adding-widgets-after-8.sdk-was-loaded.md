# 🔎 Adding widgets after 8.SDK was loaded

If you add 8SELECT widgets asynchronous the 8.SDK has to be informed about new widgets via its API.

```javascript
// failsafe if the 8.SDK is not yet injected
if (typeof _8select === "undefined") {
  return
}
// scan DOM for new 8SELECT widgets and fill with content
_8select.initCSE();
```
