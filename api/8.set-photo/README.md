---
description: Query 8.SET Photo sets
---

# 8.SET Photo

## Photo sets

This example illustrates fetching 8.SET Photo sets using pagination and tag filters.

{% hint style="warning" %}
Currently the 8.SET Photo GraphQL API only returns set definitions without any product data. For details see [graphql-schema.md](../general/graphql-schema.md "mention")
{% endhint %}

{% tabs %}
{% tab title="GraphQL Query" %}
```graphql
query {
  setPhoto(after: "6e11a3df-a3a2-4828-a292-29976bfe0696", first: 2, input: {queryType: TAGS, value: {exclude: ["summer"], include: []}}) {
    edges {
      node {
        id:
        tags
        title
        images {
          edges {
            node {
              url
            }
          }
        }
      }
    }
    pageInfo {
      endCursor
      hasNextPage
    }
  }
}

```
{% endtab %}

{% tab title="Request" %}
```bash
curl https://api.8select.io/graphql \
-H 'x-api-id: <Your API ID>'  \
-H 'Content-Type: application/json' \
-d '{"query":"{\n  setPhoto(after: \"6e11a3df-a3a2-4828-a292-29976bfe0696\", first: 2, input: {queryType: TAGS, value: {exclude: [\"summer\"], include: []}}) {\n    edges {\n      node {\n        id\n        tags\n        title\n        images {\n          edges {\n            node {\n              url\n            }\n          }\n        }\n      }\n    }\n    pageInfo {\n      endCursor\n      hasNextPage\n    }\n  }\n}\n"}'
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "data": {
    "setPhoto": {
      "edges": [
        {
          "node": {
            "id": "95405aba-4eb5-45dc-93d8-1c13bd5c5d49",
            "tags": ["winter"],
            "title": "Winter style inspiration",
            "images": {
              "edges": [
                {
                  "node": {
                    "url": "..."
                  }
                },
                {
                  "node": {
                    "url": "..."
                  }
                }
              ]
            }
          }
        },
        {
          "node": {
            "id": "d873cc15-f3ed-4d34-b313-288ead41f9a8",
            "tags": ["autumn"],
            "title": "Autumn forest look",
            "images": {
              "edges": [
                ...
                {
                  "node": {
                    "url": "..."
                  }
                }
              ]
            }
          }
        }
      ],
      "pageInfo": {
        "endCursor": "d873cc15-f3ed-4d34-b313-288ead41f9a8",
        "hasNextPage": true
      }
    }
  }
}
```
{% endtab %}
{% endtabs %}
