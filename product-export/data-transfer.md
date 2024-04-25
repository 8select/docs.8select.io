# Data Transfer

We support two main ways of transferring product data between your shop and our infrastructure.

## Pull

We periodically download your product data files from a given origin using any of the following protocols:

* HTTP(S)
  * requires a `"Content-Type"` header indicating the feed format, e.g. `text/csv`
  * supports optional `gzip` compression, if specified in a `"Content-Encoding"` header
* (S)FTP
  * requires a file extension indicating the feed format, e.g. `.csv`
* AWS S3
  * requries a `"Content-Type"` metadata indicating the feed format, e.g. `text/csv`

Each of these protocols can be used with and without credentials — if you have non-standard requirements, just talk to us and we'll find a way :yellow\_heart:

## Push

You upload your product data files whenever something updates to our S3 bucket.\
You request a signed upload URL from our API and can then upload your file. You just need to make 2 simple HTTP calls for that.

{% hint style="success" %}
Your files are encrypted on our side and can not be accessed from the outside.
{% endhint %}

![](<../.gitbook/assets/Product Import - Frame 1 (1).jpg>)

### How it works

1. Send a HTTP POST request to `api.8select.io/feeds/uploads` to retrieve a pre-signed upload request, i.e. a JSON object containing the following properties:
   * `headers`: A map of string key-value pairs
   * `method`: A HTTP method, e.g. `PUT`
   * `url`: A presigned URL
2. Send a second HTTP request using the `method` and `url`, **and including all** `headers` returned by the previous request, as well as the file to be uploaded in the HTTP body.

### API

#### get a pre-signed request for product feed upload

<mark style="color:green;">`POST`</mark> `https://api.8select.io/feeds/uploads`

#### Headers

| Name                                           | Type             | Description                     |
| ---------------------------------------------- | ---------------- | ------------------------------- |
| x-api-id<mark style="color:red;">\*</mark>     | String           | Your API ID provided by us.     |
| x-api-secret<mark style="color:red;">\*</mark> | String           | Your API SECRET provided by us. |
| content-type<mark style="color:red;">\*</mark> | application/json |                                 |

#### Request Body

| Name                                         | Type   | Description                                                                            |
| -------------------------------------------- | ------ | -------------------------------------------------------------------------------------- |
| identifier<mark style="color:red;">\*</mark> | String | The field by which a record can be uniquely identified, e.g. `"sku"` or `"productId"`  |
| format<mark style="color:red;">\*</mark>     | Object | { "options": { "delimiter": "," }, "type": "csv" }                                     |

#### Response

{% tabs %}
{% tab title="200: OK " %}
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
{% endtab %}
{% endtabs %}



#### API usage example via cURL

This is just for demonstration purposes. You can use this method to make a test upload. For production use you should do this programatically with code on your server. :sunglasses:

Replace `your-api-secret` and `your-api-secret` with your credentials.

{% tabs %}
{% tab title="get presigned URL" %}
{% code overflow="wrap" lineNumbers="true" %}
```bash
curl -v -X POST "https://api.8select.io/feeds/uploads" -d '{ "identifier": "sku", "format": { "type": "csv","options": { "delimiter": ","}}}' -H "x-api-id:your-api-id" -H "x-api-secret:your-api-secret" -H "content-type:application/json"
```
{% endcode %}
{% endtab %}

{% tab title="upload file" %}
{% code overflow="wrap" lineNumbers="true" %}
```bash
curl -X PUT -T /path/to/your/file -H "Content-Type: text/csv" -H "X-Amz-Meta-Delimiter:," -H "X-Amz-Meta-Delta:false" -H "X-Amz-Meta-Identifier:sku" \
        "https://s3.eu-central-1.amazonaws.com/......"
```
{% endcode %}
{% endtab %}
{% endtabs %}
