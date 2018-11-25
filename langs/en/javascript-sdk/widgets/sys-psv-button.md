# SYS-PSV Button

The SYS-PSV-Button informs the user of the website that a matching product set is available for the current item. The user can scroll down or jump directly to the product set with a click on the button.

Any element with the attribute `data-8select-widget-id =" sys-psv-button "` is recognized as a SYS-PSV button. This element should be hidden initially. By defining a callback the button is displayed only, when a product set is available for the current item.

**Example**

```text
<button
    data-8select-widget-id="sys-psv-button"
    onclick="_8select.utils.goToWidget(document.querySelectorAll('[data-8select-widget-id=sys-psv]')[0].getAttribute('data-8select-widget-uuid'), 0);"
    ontouchend="_8select.utils.goToWidget(document.querySelectorAll('[data-8select-widget-id=sys-psv]')[0].getAttribute('data-8select-widget-uuid'), 0);"
    type="submit"
    style="display: none;"
  >Passender Look</button>
```

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

```text
_8select.utils.goToWidget(widgetUuid, offset)
```

