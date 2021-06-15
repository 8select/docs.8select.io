---
description: >-
  All API requests must be authorized through your API ID in the HTTP request
  headers.
---

# Authentication

{% hint style="info" %}
To obtain your API ID for use with the 8SELECT API, please speak to your account manager.
{% endhint %}

Your API ID is permanently linked to your 8SELECT account. It must be included in every call to the API as a `x-api-id` header to authorize your request:

```text
POST /graphql
Host: https://api.8select.io
x-api-id: <Your API ID>
```

