# File Format

We currently only support CSV format.\
Each line will hold a purchasable product variant aka SKU.

{% hint style="info" %}
You can not provide files in CSV format? No problem, talk to us and we will find a solution. :heart:
{% endhint %}

## CSV Format

* Column separator is a comma `;`
* Wrap all values in the text qualifier double-quote `"`
* For multi-value fields use a comma `,` to separate values
* Encoding is UTF-8

## Contents

A product export can either contain all of your product catalogue or only parts of it.

If you are able to send updates on demand or can send a delta (i.e. only include changed products since the last export) you can do so as well. If not you can just send all products.

In case you can only export in stock products that is also fine.\
We treat products that where in an export in the past but are not inside an export for more than 24 hours as out of stock. So in general it is better to also include out of stock products in an export, to reflect stock changes immediately.\


{% hint style="info" %}
You should send us a full export every 24 hours - that way we can make sure everything is in sync.
{% endhint %}

## Examples

Here are two examples for you.:bulb:

{% file src="../.gitbook/assets/product-export-example-full.csv" %}
full example
{% endfile %}

{% file src="../.gitbook/assets/product-export-example-update.csv" %}
stock and price update example
{% endfile %}

{% hint style="warning" %}
Prices and stock levels can change very fast. To ensure that 8SELECT and the shop are in sync we recommend that you deliver one full export every 24 hours and an extra stock-price-update more often - up to every 15 minutes.
{% endhint %}
