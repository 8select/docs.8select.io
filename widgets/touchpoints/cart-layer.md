# Cart Layer

Show content on a modal after a product was added to the cart.



<figure><img src="../../.gitbook/assets/Screenshot 2023-10-09 at 15.08.13.png" alt=""><figcaption></figcaption></figure>

## Show complementary products via 8.SET

{% code overflow="wrap" %}
```html
<div data-8select-widget-id="8.SET" data-sku="insert-sku-of-currently-added-product" data-touchpoint="cart-layer"></div>
```
{% endcode %}

## Show similar items via 8.SIMILAR

{% code overflow="wrap" %}
```html
<div data-8select-widget-id="8.SIMILAR" data-sku="insert-sku-of-added-viewed-product" data-touchpoint="cart-layer"></div>
```
{% endcode %}

## Integration

1. when a product is added to the cart, add the widget element where you would like to show recommendation content including `data-sku`
2. call `_8select.initCSE()` to let the SDK discover the new widget
