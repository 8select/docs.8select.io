# Single Page Application

If your shop is powered by a SPA you have to make sure to "tell" the SDK about updated widget configurations.

Any widget that has some kind of dynamic configuration that will influence wich content is shown has to be replaced whenever the configuration changes. After that is done the SDK has to be informed about the change. 

{% hint style="info" %}
In the future the SDK will get smarter and recognise widget configurations automatically. For now it is necessary to go the extra mile and rerender the widget. ❤️
{% endhint %}

## How to "tell" the SDK about updated widget configurations

* change the configuration for example for the sku `data-sku="${new-sku}"`
* also update a property that will make your SPA rerender the component
  * [React](https://reactjs.org/docs/reconciliation.html#keys): `key=${new-sku}` 
  * Vue.js: `:key=${new-sku}`
* after the component is rendered call `_8select.initCSE()`

