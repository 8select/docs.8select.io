---
description: >-
  At 8SELECT we are working towards providing centralized access to all of our
  products using GraphQL as the main API technology.
---

# Introduction

## What is GraphQL?

GraphQL is a query language for clients to fetch data they need from an API. It is defined through a [**specification**](http://spec.graphql.org), which describes how data should be requested and formatted in a response. 

GraphQL is strongly typed and well structured. That means, an API will not only define **and guarantee** what type of data each field in its schema can be, but also define the links and relationships between any complex objects. This enables queries to fetch exactly the information they need by specifying either a single object or traversing any links in the structure to request related information in a single query.

### Why use GraphQL?

At 8SELECT we use GraphQL primarily because it enables developers to make API calls which gets them exactly what data they need in the simplest way possible. Since it is a well structured schema you can fetch data and know that you will get the data back in a guaranteed format and because of that, tooling can make development significantly easier.

### How to query GraphQL?

Most commonly GraphQL can be queried by making HTTP `POST` requests to its respective endpoint. At 8SELECT this endpoint currently is `https://api.8select.io`**`/graphql`**. To make a request you can use cURL or any other HTTP compatible client.

Currently we only support `productSets` as a top-level resolver in our query schema. Given a specific product identifier, it will return a list of **8.SET Compose** product sets. Assuming you have a product with the SKU `123456-7890` in your catalogue,  you could use the following example to query the titles of respective product sets:

```text
productSets(input: {queryType: SKU, value: "123456-7890"}) {
    edges {
        node {
            title
        }
    }
}
```

To send this query to the GraphQL endpoint you would use the following request:

```text
POST /graphql
Host: https://api-demo.8select.io
Content-Type: application/json
x-api-id: <Your API ID>
{
    "query": "{ productSets(input: {queryType: SKU, value: \"123456-7890\"}) { edges { node { title } } } }"
}
```

Using `curl`, you could make the request with the following call:

```text
curl https://api-demo.8select.io/graphql \
     -H 'Content-Type: application/json' \
     -H 'x-api-id: <Your API ID>' \
     -d '{ "query": "{ productSets(input: {queryType: SKU, value: \"123456-7890\"}) { edges { node { title } } } }" }'
```

#### Further Information

To find out more, read the official [**GraphQL documentation**](https://graphql.org/learn/) and learn about writing efficient [**GraphQL queries**](https://graphql.org/learn/queries/). 


