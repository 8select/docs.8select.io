---
description: >-
  At 8SELECT we are working towards providing centralized access to all of our
  products using GraphQL as the main API technology.
---

# Introduction

## What is GraphQL?

GraphQL is a query language for clients to fetch data they need from an API. It is defined through a [**specification**](http://spec.graphql.org), which describes how data should be requested and formatted in a response.&#x20;

GraphQL is strongly typed and well structured. That means, an API will not only define **and guarantee** what type of data each field in its schema can be, but also define the links and relationships between any complex objects. This enables queries to fetch exactly the information they need by specifying either a single object or traversing any links in the structure to request related information in a single query.

### Why use GraphQL?

At 8SELECT we use GraphQL primarily because it enables developers to make API calls which gets them exactly what data they need in the simplest way possible. Since it is a well structured schema you can fetch data and know that you will get the data back in a guaranteed format and because of that, tooling can make development significantly easier.

### How to query GraphQL?

Most commonly GraphQL can be queried by making HTTP `POST` requests to its respective endpoint. At 8SELECT this endpoint currently is `https://api.8select.io/graphql`. To make a request you can use cURL or any other HTTP compatible client. There are also various GraphQL specific clients available in different programming languages.

You get query content for a given product identifier or query a specific custom-set.

Assuming you have a product with the SKU `8S-DEMO-Polohemd-1` in your catalogue,  you could use the following example to query a list of similar products.

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

To send this query to the GraphQL endpoint you would use the following request in `curl`

```bash
curl --request POST \
  --url https://api.8select.io/graphql \
  --header 'Content-Type: application/json' \
  --header 'x-api-id: db54750f-80fc-4818-9455-30ca233225dc' \
  --data '{"query":"query {\n  product(id: \"8S-DEMO-Polohemd-1\") {\n    similarProducts(first: 5) {\n      edges {\n        node {\n          id\n        }\n      }\n    }\n  }\n}\n"}'
```

And the result will be a list of similar products limited to the first 5

```json
{
  "data": {
    "product": {
      "similarProducts": {
        "edges": [
          {
            "node": {
              "id": "8S-DEMO-Polohemd-10"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-9"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-7"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-8"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-2"
            }
          }
        ]
      }
    }
  }
}
```

#### Further Information

To find out more about GraphQL in general, read the official [**GraphQL documentation**](https://graphql.org/learn/) and learn about writing efficient [**GraphQL queries**](https://graphql.org/learn/queries/).&#x20;

