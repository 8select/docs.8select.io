# Data transfer

Currently we support the transfer of data by pulling a REST API \(8SELECT specification\) or by file download.

## REST API

* REST API \(specification on request\)
  * our plugins for Shopware, Oxid and JTL-Shop currently use this method for data transfer

## File download

### Protocols

* File Storage, for example
  * sFTP
  * AWS S3
* HTTPS

### Format

We can retrieve the product data in almost any format. We prefer a deliver as CSV with the data of a product variant \(SKU\) per line.

{% file src="../.gitbook/assets/datenexport-beispiel.csv" caption="Full export example" %}

{% file src="../.gitbook/assets/datenexport-beispiel-preise-bestand.csv" caption="Extra stock- price-update example" %}

{% hint style="warning" %}
Prices and stock levels can change very fast. To ensure that 8SELECT and the shop are in sync we recommend that you deliver one full export every 24 hours and an extra stock- price-update more often - up to every 15 minutes.
{% endhint %}

