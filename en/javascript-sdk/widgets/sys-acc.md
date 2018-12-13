# SYS-ACC

## Widget element

```markup
<div data-8select-widget-id="sys-acc" data-sku="42" data-include-css="true"></div>
```

### Parameter

`data-sku` is the SKU of the current item. The CSE searches a matching product set that contains this item. The value for `data-sku` must be set dynamically and must match one of the SKU or master SKU passed in the master data feed.

`data-include-css` can be `true` or `false`. If the value is omitted, the value corresponds to `false`. If the value is set to `true` a basic CSS for a CSS grid based on [https://purecss.io/grids/](https://purecss.io/grids/) is generated. In addition, CSS declarations are set for individual elements. Newly added elements for example are hidden by the declaration `display: none`.

### CSS classes

Following CSS classes are used. For some classes, default values ​​are set. These can be overwritten by `!important`.

```css
.-eightselect-item-list {
}

.-eightselect-item {
}

.-eightselect-item-image {
}

.-eightselect-item-body {
}

.-eightselect-item-brand {
}

.-eightselect-item-name {
  display: none;
}

.-eightselect-item-sales-price {
}

.-eightselect-item-stroke-price {
}
```

### Example of customizing CSS

The following CSS example inserts a euro symbol \(€ \) before the price, formats the recommended retail price and transforms the brand into capital letters. In addition, the recommended retail price and resale price are displayed side by side and images are centered.

```css
.-eightselect-item-image,
.-eightselect-item-body {
    text-align: center;
}
.-eightselect-item-brand {
    text-transform: uppercase;
}
.-eightselect-item-stroke-price {
    text-decoration: line-through;
}
.-eightselect-item-sales-price,
.-eightselect-item-stroke-price {
    display: inline-block;
}
.-eightselect-item-sales-price::before,
.-eightselect-item-stroke-price::before {
    content:"€ ";
}
```

### Example response of endpoint

The HTML of the returned widget has the following structure:

```markup
<div class="-eightselect-item-list -eightselect-g">
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
    <div class="-eightselect-item -eightselect-u-1-4">
        <a href="#">
            <div class="-eightselect-item-image">
                <img src="" />
            </div>
            <div class="-eightselect-item-body">
                <div class="-eightselect-item-brand">Hugo Boss</div>
                <div class="-eightselect-item-name">Sakko</div>
                <div class="-eightselect-item-stroke-price">299,99</div>
                <div class="-eightselect-item-sales-price">249,99</div>
            </div>
        </a>
    </div>
</div>
```

### Initialize Widget element if the widget is subsequently written to the DOM

Like all other widgets, the SYS-ACC widget is automatically recognized by the `widget-loader`, as long as the widget is present in the DOM before the `widget-loader`.

If the widget element is added to the DOM later, for example, by a modal which is filled via an AJAX call, then the widget element must be initialized manually.

```text
window._8select.initCSE();
```

## SYS-ACC Callback

In case of success or error `window._eightselect_config['sys-acc'].callback` is called, as long as a function is defined.

### **Example**

```text
window._eightselect_config = window._eightselect_config || {}
window._eightselect_config['sys-acc'] = {
  callback: function (error, sku, widgetUuid) {
    if (error) {
      // something went wrong or no set was found for given sku
      alert('uh oh')
      return
    }
    // everything fine and a set was found for given sku
    alert('YEAH BABY!')

  }
}
```

