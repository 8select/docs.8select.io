# SYS-PSV Button

Der SYS-PSV-Button weißt den Nutzer der Webseite darauf hin, dass es zum aktuell angesehenen Artikel ein passendes Produktset gibt.  
Der Nutzer kann mit einem Klick auf den Button direkt zum Produktset runterscrollen oder springen.

Ein beliebiges Element mit dem Attribut `data-8select-widget-id="sys-psv-button"` wird als SYS-PSV Button erkannt. Dieses Element sollte initial versteckt sein. Durch die Definition eines Callbacks wird der Button eingeblendet, wenn ein Produktset zum Artikel verfügbar ist.

**Beispiel**

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

