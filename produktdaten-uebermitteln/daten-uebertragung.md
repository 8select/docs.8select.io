# Data Transfer

Currently we support the transfer of data by pulling a REST API (8SELECT specification) or by file download.

## File download

### Protocols

* File Storage, for example
  * sFTP
  * AWS S3
* HTTPS

### Format

We can retrieve the product data in almost any format.&#x20;

We prefer a delivery as CSV with the data of a product variant (SKU) per line. Here are two examples.

{% file src="../.gitbook/assets/fashion-content-pool-full-example.csv" %}
fashion content pool full example
{% endfile %}

{% file src="../.gitbook/assets/stock-price-example (1).csv" %}
stock and price update example
{% endfile %}

{% hint style="warning" %}
Prices and stock levels can change very fast. To ensure that 8SELECT and the shop are in sync we recommend that you deliver one full export every 24 hours and an extra stock- price-update more often - up to every 15 minutes.
{% endhint %}
