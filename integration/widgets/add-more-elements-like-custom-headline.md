# ➕ Add more elements, like custom headline

You can add any extra elements on top or below the widget.\
\
For example if you want to add your own custom headline markup.&#x20;

You just wrap the widget inside another `div` element and apply the css-class `-eightselect-widget-container`.

```html
<div class="-eightselect-widget-container">
    <div class="some-complicated markup">
        <h2>Complementary products you may like</h2>
        <div class="some-horizontal-spacer"></div>
    </div>
    <div data-8select-widget-id="8.SET" data-touchpoint="product" data-sku="42"></div>
</div>
```

In case there is no content or something prevents the SDK to show the widget, the whole recommendation area is hidden.
