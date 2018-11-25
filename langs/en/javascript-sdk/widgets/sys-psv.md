# SYS-PSV

```markup
<div data-8select-widget-id="sys-psv" data-sku="42"></div>
```

`data-sku` is the SKU of the current item. The CSE searches a matching product set that contains this item. The value for `data-sku` must be set dynamically and must match one of the SKU or master SKU passed in the master data feed.

## Reload SYS-PSV widget with other SKU

If your shop reloads variants via Ajax, you must inform the SYS-PSV widget about the changed SKU.

```javascript
window._8select.reinitSys("<neue-sku>", "<alte-sku>");
```

## SYS-PSV Callback

In case of success or error `window._eightselect_config.sys.callback` is called, as long as a function is defined.

**Example**

```text
window._eightselect_config = window._eightselect_config || {}
window._eightselect_config['sys'] = {
  callback: function (error, sku, widgetUuid) {
    if (error) {
      // something went wrong or no set was found for given sku
      return
    }
    // everything fine and a set was found for given sku
    // we can show a button that let's the customer know that we have a set and allows him/her to navigate to the widget with one click
    document.querySelector('[data-8select-widget-id=sys-psv-button]').style.display = 'block'
  }
}
```

