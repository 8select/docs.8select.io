---
description: Base product data we need to playout any content
---

# Base Data

In order to be able to display the products meaningfully in the widgets, a basic set of data must be transmitted.&#x20;

### Required properties

If a property has multiple values those should be separated by a pipe `|`.

* SKU
  * primary identifier used in widgets and tracking
* Main-SKU (Parent-SKU)
  * identifier for group of product variants (size only)
* Model
  * identifier for group of product variants (colors etc.)
* Status
  * Flag 0/1 or current stock level
* Size
* Name
* Retail price and discount price
* Deeplink to product variant in shop
* Images
  * All available images in maximum resolution. For an optimal presentation at least one cut out image (hollow man photography).
  * Transfer images with least possible fillup / whitespace to optimize the presentation in the widgets.

{% hint style="danger" %}
We deliver image thumbnails from our CDN and cache images heavily. If you change images you have to also change the image URL in order to invalidate the CDN cache!&#x20;
{% endhint %}

{% hint style="info" %}
In order to access our Fashion Content Pool, further data is required. See [**Fashion Content Pool**](../fashion-content-pool/).
{% endhint %}

### Examples

{% file src="../../.gitbook/assets/base-data-example (1).csv" %}
base data example
{% endfile %}

{% hint style="info" %}
Prices and stock levels can change very fast. To ensure that 8SELECT and the shop are in sync we recommend that you deliver one full export every 24 hours and an extra stock- price-update more often - up to every 15 minutes.
{% endhint %}

{% file src="../../.gitbook/assets/stock-price-example (1).csv" %}
stock and price update example
{% endfile %}

{% content-ref url="details.md" %}
[details.md](details.md)
{% endcontent-ref %}

