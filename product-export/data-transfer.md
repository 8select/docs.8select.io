# Data Transfer

Currently we support some push and pull methods to transfer your product data.

## Pull

We download your product data files on a schedule. You just tell us from where and when.

### Protocols

* File Storage like
  * FTP
  * SFTP
  * FTPS
  * AWS S3
* HTTPS
  * without credentials
  * with credentials via basic auth
  * custom login forms will probably also work, talk to us please :yellow\_heart:

## Push

You upload your product data files whenever something updates to our S3 bucket.\
You just request a signed upload URL from our API and can then upload your file. You just need to make 2 simple HTTP calls for that.

{% hint style="success" %}
Your files are encrypted and can not be accessed from the outside.
{% endhint %}

![](<../.gitbook/assets/Product Import - Frame 1 (1).jpg>)

### How it works

1. HTTP POST request to retrieve a signed upload URL.
   1. Depending on wether you want to upload a full feed or update feed you need to set different body parameters.
   2. You will get a `key` and an `uploadUrl`.
2. HTTP PUT request to the retrieved `uploadUrl`.
   1. Don't forget to include the file in the HTTP body. :-)&#x20;

### API

#### Upload Full Product Feed&#x20;

{% swagger method="post" path="/uploads" baseUrl="https://api.8select.io" summary="Get signed URL for full product feed upload." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-id" required="true" %}
Your API ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-secret" required="true" %}
Your API SECRET provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="true" %}
`productFeed`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productFeed" type="Object" required="true" %}
`{ "fileType": "text/csv" }`

 
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

#### Upload Update Product Feed&#x20;

{% swagger method="post" path="/uploads" baseUrl="https://api.8select.io" summary="Get signed URL for update product feed upload." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-id" required="true" %}
Your API ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-secret" required="true" %}
Your API SECRET provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" required="true" %}
`productUpdateFeed`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="productUpdateFeed" type="Object" required="true" %}
`{ "fileType": "text/csv" }`

 
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

## File Format

We currently only support CSV format.\
Each line will hold a product variant (SKU).

You can not provide files in CSV format? No problem, talk to us and we will find a solution. :heart:

### Examples

Here are two examples for you.:bulb:

{% file src="../.gitbook/assets/fashion-content-pool-full-example.csv" %}
fashion content pool full example
{% endfile %}

{% file src="../.gitbook/assets/stock-price-example (1).csv" %}
stock and price update example
{% endfile %}

{% hint style="warning" %}
Prices and stock levels can change very fast. To ensure that 8SELECT and the shop are in sync we recommend that you deliver one full export every 24 hours and an extra stock- price-update more often - up to every 15 minutes.
{% endhint %}