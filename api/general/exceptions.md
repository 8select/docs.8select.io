---
description: >-
  Any errors during resolution of a GraphQL query are returned as part of the
  API response.
---

# Exceptions

Using GraphQL's introspection capabilities in conjunction with respective tooling allows to avoid many potential errors already during development. However of course, not all failures can be prevented.

Since a complex GraphQL query can involve many separate data sources to resolve various fields, the resolution can fail partially and still succeed in the remaining parts.That's why a response can contain a list of `errors` in addition to a `data` property. 

## Authorization Error

Unauthorized requests cannot be resolved properly. All top-level fields in the included query will default to `null` and the failed resolutions be reported as part of the list of occured `errors`.

Let's a ssume the following query to fetch 8.SET Compose product sets for two different products from your catalogue at the same time:

```text
productA: setCompose(input: {queryType: SKU, value: "123456-7890"}) {
    edges {
        node {
            title
        }
    }
}
productB: setCompose(input: {queryType: SKU, value: "098764-4321"}) {
    edges {
        node {
            title
        }
    }
}
```

If this query would be sent in an unauthorized request \(notice the missing `x-api-id` header\):

```text
POST /graphql
Host: https://api-demo.8select.io
Content-Type: application/json
{
    "query": "{ productA: setCompose(input: {queryType: SKU, value: \"000021803-3\"}) { edges { node { title } } } productB: setCompose(input: {queryType: SKU, value: \"000021803-1\"}) { edges { node { title } } } }"}"
}
```

The result would list both failures to resolve product sets for `productA` as well as `productB`:

```text
{
  "data": {
    "productA": null,
    "productB": null
  },
  "errors": [
    {
      "path": [
        "productA"
      ],
      "data": null,
      "errorType": null,
      "errorInfo": null,
      "locations": [
        {
          "line": 2,
          "column": 3,
          "sourceName": null
        }
      ],
      "message": "Required API ID not provided"
    },
    {
      "path": [
        "productB"
      ],
      "data": null,
      "errorType": null,
      "errorInfo": null,
      "locations": [
        {
          "line": 9,
          "column": 3,
          "sourceName": null
        }
      ],
      "message": "Required API ID not provided"
    }
  ]
}
```



