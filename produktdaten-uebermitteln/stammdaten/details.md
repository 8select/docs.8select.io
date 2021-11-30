# Details and examples

## SKU (sku)

The SKU is unique. The SKU is the main identifier for a specific item (buyable physical variant) in a shop.

Variant (SKU): Shirt Arie - color blue - size M

### Examples

```
8277-480-01
8febdd77-c6a6-40f6-b322-9620680c7bc2
42
A-2-21
```

{% hint style="warning" %}
The SKU is used to find content for an item, to add an item to the shopping cart and to match purchases with interactions in our widgets. \
This means that this value must also be available in the shop for the widgets and in the checkout.
{% endhint %}

## Main-SKU (main-sku)

The Main-SKU is unique, it contains the model and colour. The Main SKU is the main identifier for an item (parent item) in a shop.&#x20;

The Main-SKU is used to establish a relationship between parent items and size variants.\
\
Parent item (Main-SKU): Shirt Arie - color blue\
Variant (SKU): Shirt Arie - color blue - size M

### Examples

```
8277-480
Shirt-blue
```

## Model (model)

A model refers to the basic product. A model can exist in several versions that differ, for example, in size, colour or pattern.

The model `Arie` (8277) exists in three different colors: `blue` (480), `red` (481), `yellow` (482) and in four different sizes: `S` (01), `M` (02), `L` (03), `XL` (04). All combined will make up to 12 different variants. Each variant has its own SKU.\
\
Model: Shirt Arie\
Parent item (Main-SKU): Shirt Arie - color blue\
Variant (SKU): Shirt Arie - color blue - size M

### Examples

| model      | main-sku              | sku                          |
| ---------- | --------------------- | ---------------------------- |
| 8277       | 8277-480              | 8277-480-01                  |
| shirt-arie | shirt-arie-color-blue | shirt-arie-color-blue-size-m |

## Stock (status)

The value provides information about the availability of a variant. It can be a flag (0/1) or the quantity of available items.

### Examples

available

```
1
3
12
```

not available

```
0
```

## Size (size)

Size of the item.

### Beispiele

```
38
L
32/32
32 L
M-L
```

## Name (name)

Default name for the item as it is normally used on the product page.

### Examples

```
Desigual Sweatshirt
Evelyne GM 33
```

## Retail price (retail-price)

The original price or RRP. \
Usually shown as a crossed-out price in the shop.&#x20;

Without currency and in cents.

### Examples

```
8000
19939
```

## Discount price (discount-price)

The price at which the item is sold.&#x20;

Without currency and in cents.

### Examples

```
6995
13750
```

## Product URL (product-url)

Deep link that leads directly to the detail page in the shop of the variant.

### Examples

```
https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387
https://www.bettybarclay.com/de/vera-mont-cocktail-kleid-21254528.html?farbe=burnished-ros&groesse=38
```

## Images (images)

All available item images of the variant in the highest resolution. Multiple images are separated with pipe `|`. Position 1 is ideally a hollow man image or product image without model.

### Examples

```javascript
https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$

https://cdn.8select.io/image1.jpg|https://cdn.8select.io/image2.jpg
```
