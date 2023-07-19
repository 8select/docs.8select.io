---
description: Base product data we need to playout any content
---

# Base Data

In order to be able to display the products meaningfully in the widgets, a basic set of data must be transmitted.&#x20;

### Required properties

If a property has multiple values those should be separated by a comma `,`.

* SKU
  * primary identifier used in widgets and tracking
* Main-SKU (Parent-SKU)
  * identifier for group of product variants (size only)
* Model
  * identifier for group of product variants (colors etc.)
* Stock
  * current stock level or flag 0/1
* Variant
  * name of variant (size) - for example `L, M, 32/34, 42, 150 ml`
* Name
  * product name
* Category paths
  * breadcrumbs used in the shop - for example `Women > Clothes > Jackets > Blazer`
  * if product is in multiple paths use a comma `,` as a separator
* Brand
* Retail price
* Discount price
* Lowest price in the last 30 days\*
  * only if required by law in your country
* Deeplink to product variant in shop
  * either to variant where the user then needs to choose the size or directly to the SKU
* Image
  * Main image in maximum resolution. Used for data tagging via image recognition.
  * For an optimal recognition use the cut out image (hollow man photography) without any other objects / persons.
* Thumbnail
  * Main image in smaller resolution. Used for widget content.
  * Use image with least possible fillup / whitespace to optimize the presentation in the widgets
  * For an optimal presentation use the cut out image (hollow man photography) without any other objects / persons.

{% hint style="danger" %}
In case you can not provide a thumbnail, we deliver image thumbnails from our CDN and cache images heavily. If you change images you have to also change the image URL in order to invalidate the CDN cache!&#x20;
{% endhint %}

{% hint style="info" %}
In order to access our Fashion Content Pool, further data is required. See [**Fashion Content Pool**](../fashion-content-pool/).
{% endhint %}

{% content-ref url="details.md" %}
[details.md](details.md)
{% endcontent-ref %}

