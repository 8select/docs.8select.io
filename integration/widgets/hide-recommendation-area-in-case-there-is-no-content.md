# 👻 Hide recommendation area in case there is no content

It may happen that we can not provide recommendation content for some reason. The widgets will only show up in case there is content and no error.

In case you add your own headline or some other element that should also be hidden in case the is no content, you can just add the CSS class `-eightselect-widget-container` to the most outer HTML element. That will allow the 8.SDK to hide the whole recommendation area.

The container element will be set to `display:block` in case there is content. So you can initially just hide the element.



```html
<div class="-eightselect-widget-container" style="display:none">
    <h2>Complementary products you may like</h2>
    <div data-8select-widget-id="8.SET" data-touchpoint="product" data-sku="42"></div>
</div>
```