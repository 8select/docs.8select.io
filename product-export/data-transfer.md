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

1. Send a HTTP POST request to `api.8select.io/feeds/uploads` to retrieve a pre-signed upload request, i.e. a JSON object containing the following properties:
   * `headers`: A map of string key-value pairs
   * `method`: A HTTP method, e.g. `PUT`
   * `url`: A presigned URL
2. Send another HTTP request using the `method` and `url`, **and including all** `headers` returned by the previous request, as well as the file to be uploaded in the HTTP body.

### API

#### Upload Product Feed&#x20;

{% swagger method="post" path="/feeds/uploads" baseUrl="https://api.8select.io" summary="Get a pre-signed request for product feed upload." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-id" required="true" %}
Your API ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-secret" required="true" %}
Your API SECRET provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="format" required="true" type="" %}
`"csv"`
{% endswagger-parameter %}

{% swagger-parameter in="body" name="config" type="Object" required="true" %}
`{ "delimiter": ",", "skuFieldName": "sku" }`

 
{% endswagger-parameter %}

{% swagger-parameter in="header" name="content-type" required="true" type="application/json" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```typescript
{
    "headers": {
        "Content-Type": "text/csv; charset=utf-8", // depending on the request parameters
        "X-Amz-Meta-Delimiter": ",", // depending on the request parameters
        "X-Amz-Meta-Sku-Field-Name": "sku", // depending on the request parameters
        ... // could be more
    },
    "method": "PUT",
    "url": "https://s3.eu-central-1.amazonaws.com/..."
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
