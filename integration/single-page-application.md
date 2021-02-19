# Single Page Application

If your shop is powered by a SPA you have to make sure to "tell" the SDK about updated widget configurations.

Any widget that has some kind of dynamic configuration that will influence wich content is shown has to be updated and reinitiated whenever a user navigates to a page with that widget.

## 8.SET Compose example

* widget is integrated on product-detail page \(PDP\)
* we have a product with SKU 42 \(P42\)
* we have a product with SKU 21 \(P21\)

### User flow

1. user navigates to PDP of P21
   * the 8.SDK Web has to be loaded
   * the 8.SET Compose widget has to be present in the DOM
     * `data-sku` has to be set to SKU of P21, i.e. "21"
   * if the widget was added after 8.SDK Web was loaded you have to tell the SDK to scan the DOM again
     * `_8select.util.initCSE()`
2. 8.SDK scans DOM and finds widget 8.SET Compose and initialises it
3. If there is 8SELECT content for P21 the widget is filled with the actual 8.SET Compose content and shown to the user
   1. If there is no content the widget will stay empty and invisible to the user
4. user navigates to PDP of P42
   1. the 8.SDK Web is already loaded
   2. the 8.SET Compose widget should already be present in the DOM
      1. ⚠️ update widget configuration by calling `_8select.reinitSys('42')`
5. If there is 8SELECT content for P42 the widget content is updated
   1. If there is no content the widget will content will be emptied and made invisible to the user

## 8.SET Flat example

* widget is integrated on a modal that is opened when user adds product to cart
* we have a product with SKU 42 \(P42\)
* we have a product with SKU 21 \(P21\)

### User flow

1. user navigates to PDP of P21 and adds it to cart
2. a modal is shown "P21 added to cart - you might be interested in those products"
   * the 8.SDK Web has to be loaded
   * the 8.SET Flat widget has to be present in the DOM \(probably in the modal HTML\)
     * `data-sku` has to be set to SKU of P21, i.e. "21"
   * if the widget was added after 8.SDK Web was loaded you have to tell the SDK to scan the DOM again
     * `_8select.util.initCSE()`
3. 8.SDK scans DOM and finds widget 8.SET Flat and initialises it
4. If there is 8SELECT content for P21 the widget is filled with the actual 8.SET Flat content and shown to the user
   1. If there is no content the widget will stay empty and invisible to the user
5. user navigates away from page
   1. Option a\) the modal that was shown is destroyed
      1. the 8.SET Flat widget also has to be destroyed
         1. `_8select.utils.widgetLoader.findWidgetByType('SysAcc').destroy()`
      2. if another product is added to the cart the flow restarts at 2. 
   2. Option b\) the modal is just closed / hidden
      1. the 8.SET Flat widget also has to be destroyed
         1. `_8select.utils.widgetLoader.findWidgetByType('SysAcc').destroy()`
      2. if another product P42 is added to the cart the widget configuration has to be updated
      3. update widget configuration by manipulating the `data-sku` attribute
         1. `_8select.utils.widgetLoader.findWidgetByType('SysAcc').node.setAttribute('data-sku', '21')`
      4. tell the SDK to initialise the widget again
         1. `_8select.util.initCSE()`

