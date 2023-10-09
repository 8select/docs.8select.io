# Data Transfer

Currently we support push and pull methods to transfer your product data.

{% hint style="success" %}
Your files are encrypted on our side and can not be accessed from the outside.
{% endhint %}

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
You request a signed upload URL from our API and can then upload your file. You just need to make 2 simple HTTP calls for that.

![](<../.gitbook/assets/Product Import - Frame 1 (1).jpg>)

### How it works

1. Send a HTTP POST request to `api.8select.io/feeds/uploads` to retrieve a pre-signed upload request, i.e. a JSON object containing the following properties:
   * `headers`: A map of string key-value pairs
   * `method`: A HTTP method, e.g. `PUT`
   * `url`: A presigned URL
2. Send a second HTTP request using the `method` and `url`, **and including all** `headers` returned by the previous request, as well as the file to be uploaded in the HTTP body.

### API

#### Upload Product Feed&#x20;

{% swagger method="post" path="/feeds/uploads" baseUrl="https://api.8select.io" summary="Get a pre-signed request for product feed upload." expanded="true" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="x-api-id" required="true" type="String" %}
Your API ID provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="x-api-secret" required="true" type="String" %}
Your API SECRET provided by us.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="identifier" required="true" type="String" %}
The field by which a record can be uniquely identified, e.g. `"sku"` or `"productId"`&#x20;
{% endswagger-parameter %}

{% swagger-parameter in="body" name="format" type="Object" required="true" %}
{ "options": { "delimiter": "," }, "type": "csv" }
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
