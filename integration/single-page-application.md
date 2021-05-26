# Single Page Application

If your shop is powered by a SPA you have to make sure to "tell" the SDK about updated widget configurations.

Any widget that has some kind of dynamic configuration that will influence wich content is shown has to be replaced whenever the configuration changes. After that is done the SDK has to be informed about the change. 

{% hint style="info" %}
In the future the SDK will get smarter and recognise widget configurations automatically. For now it is necessary to go the extra mile and rerender the widget. ❤️
{% endhint %}

## How to "tell" the SDK about updated widget configurations

### When is this necessary?

Some examples for 8.SET Compose:

* the product variant \(other than size\) is changed, for example if your customers can select the color or pattern as a variant of a product
* the product completely changes, i.e. if the customer navigates to another product page

### How to implement it?

* change the configuration for example for the SKU `data-sku="${new-sku}"`
* **required:** also update a property that will make your SPA rerender the component
  * [React](https://reactjs.org/docs/reconciliation.html#keys): `key={new-sku}` 
  * Vue.js: `:key={new-sku}`
* after the component is rendered call `_8select.initCSE()`

## Navigate to product page via SPA router

Inside our widgets a user can click on a product and will be redirected to the corresponding product page in your shop. This is done by changing the browsers location, i.e. `window.location.href`.

We can configure most widgets to make use of your SPA router if you provide a way to access the functionality via JavaScript. For example we could call something like `window.myFancyRouter.push("/path/to/product/user/wants/to/visit.html")`

