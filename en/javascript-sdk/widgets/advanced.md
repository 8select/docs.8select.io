# Advanced

## Callbacks

Some widgets call an error-first callback on success or failure. For example, it can display alternative content instead of the widget, if no product set is currently available for a particular product.

## Lazy Loading

To load widgets only if they are in the visible area or in a certain distance to the visible area, the attribute `data-load-distance-factor` can be set.

`data-load-distance-factor` is optional and can be a number greater or equal to `0`. The value describes the factor from what distance to the bottom part of the visible area, the widget is loaded. See the following [Illustration](./#file-wgt-ldr-lazy-load-pdf).

If the attribute is not set, all widget elements are loaded directly.

If the value is set to `0` the widget starts loading as soon as the element reaches the bottom part of the visible area.

If the value is set to `1` the widget is loaded one screen distance earlier. The higher the value, the earlier the widget is loaded.

```markup
<div data-sku="42" data-8select-widget-id="sys-psv" data-load-distance-factor="1"></div>
```

## Container elements / Headings / Extentions

The widget can be integrated anywhere in the HTML document. This way you can insert the widget seamlessly into your layout.

The 8select product sets are dynamic. There may be a larger or smaller amount of active product sets depending on the availability of items. To avoid displaying empty container elements when a specified product set is no longer available, the parent container element should be hidden initially. This means the property `display` should have the value `none`. Most important the CSS-class **must** be set to `-eightselect-widget-container`.

Once the widget and the product set are loaded, the container element, as well as the widget, appears.

**Example with container element**

```markup
<div class="teaserBox -eightselect-widget-container" style="display: none;">
    <h3 class="teaserTitle">Look der Woche</h3>
    <div class="teaserWrapper">
        <div data-8select-widget-id="psp-psv" data-set-id="365"></div>
    </div>
</div>
```

