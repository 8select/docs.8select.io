---
description: >-
  Any errors during resolution of a GraphQL query are returned as part of the
  API response.
---

# Exceptions

Using GraphQL's introspection capabilities in conjunction with respective tooling allows to avoid many potential errors already during development. However of course, not all failures can be prevented.

Since a complex GraphQL query can involve many separate data sources to resolve various fields, the resolution can fail partially and still succeed in the remaining parts. That's why a response can contain a list of `errors` in addition to a `data` property.&#x20;

## Authorization Error

Unauthorized requests cannot be resolved properly. All top-level fields in the included query will default to `null` and the failed resolutions be reported as part of the list of occured `errors`.

Let's a ssume the following query to fetch similar products:

```graphql
product(id: "8S-DEMO-Polohemd-1") {
   similarProducts(first: 5) {
      edges {
        node {
          id
        }
      }
    }
  }
}
```

If this query would be sent in an unauthorized request (notice the missing `x-api-id` header):

```bash
curl --request POST \
  --url https://api.8select.io/graphql \
  --header 'Content-Type: application/json' \
  --data '{"query":"query {\n  product(id: \"8S-DEMO-Polohemd-1\") {\n    similarProducts(first: 5) {\n      edges {\n        node {\n          id\n        }\n      }\n    }\n  }\n}\n"}'
```

The result would list the failure:

```json
{
  "data": {
    "product": null
  },
  "errors": [
    {
      "path": [
        "product"
      ],
      "data": null,
      "errorType": "Unauthorized",
      "errorInfo": null,
      "locations": [
        {
          "line": 2,
          "column": 3,
          "sourceName": null
        }
      ],
      "message": "Not Authorized to access product on type ProductReference"
    }
  ]
}
```

## Validation Error

For requests with invalid queries you will get back the information about what is wrong.

Let's assume we used a wrong argument in our query, i.e. `sku` instead of `id`:

```bash
curl --request POST \
        --url https://api.8select.io/graphql \
        --header 'Content-Type: application/json' \
        --header 'x-api-id: db54750f-80fc-4818-9455-30ca233225dc' \
        --data '{"query":"query {\n  product(sku: \"8S-DEMO-Polohemd-1\") {\n    similarProducts {\n      edges {\n        node {\n          id\n        }\n      }\n    }\n  }\n}\n"}'
```

The result would list the failure and hint on which line something is wrong:

```json
{
  "data": null,
  "errors": [
    {
      "path": null,
      "locations": [
        {
          "line": 2,
          "column": 3,
          "sourceName": null
        }
      ],
      "message": "Validation error of type MissingFieldArgument: Missing field argument id @ 'product'"
    },
    {
      "path": null,
      "locations": [
        {
          "line": 2,
          "column": 11,
          "sourceName": null
        }
      ],
      "message": "Validation error of type UnknownArgument: Unknown field argument sku @ 'product'"
    }
  ]
}
```
