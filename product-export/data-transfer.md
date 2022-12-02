# Data Transfer

Currently we support some push and pull methods to the transfer your product data.

## Pull

We download your product data files on a schedule.

### Protocols

* File Storage like
  * FTP
  * SFTP
  * FTPS
  * AWS S3
* HTTPS

## Push (Beta Preview)

You upload your product data files whenever something updates to our S3 bucket.\
You just request a signed upload URL from our API and can then upload your file. You just need to make 2 simple HTTP calls for that.

{% hint style="success" %}
Your files are encrypted and can not be accessed from the outside.
{% endhint %}

{% hint style="info" %}
Push is currently in preview and might not work for you. General availability is planned for 12/2022.
{% endhint %}

![](<../.gitbook/assets/Product Import - Frame 1 (1).jpg>)

1. HTTP POST request to retrieve a signed upload URL.
   1. You will get a `key` and an `uploadUrl`.
2. HTTP PUT request to the retrieved `uploadUrl`.
   1. The filename must match the retrieved `key`.

{% swagger method="post" path="/products/uploads" baseUrl="https://integration.8select.io" summary="" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-id" required="true" %}
Your API ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-feed-id" required="true" %}
Your FEED ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="content-type" required="true" %}
Currently we only support text/csv.
{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}
```typescript
{ 
  "key": string 
  "uploadUrl": string
}
```
{% endswagger-response %}
{% endswagger %}

## Format

We can download and process the product data in almost any format. For file uploads we only support CSV for now.

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
