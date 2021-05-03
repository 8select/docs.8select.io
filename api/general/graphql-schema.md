---
description: Full annotated GraphQL introspection schema for reference.
---

# GraphQL Schema

```graphql
schema {
    query: Query
}

type Query {
    productSets(input: ProductSetQueryInput!, first: Int): ProductSetConnection
}

enum ProductSetQueryType {
    MODEL_ID
    MAIN_SKU
    SKU
}

input ProductSetQueryInput {
    queryType: ProductSetQueryType!
    value: String!
}

type PageInfo {
    endCursor: String
}

type ProductModel {
    id: String!
}

type ProductVariant {
    sku: String!
}

type ProductVariantEdge {
    node: ProductVariant!
}

type ProductVariantConnection {
    edges: [ProductVariantEdge!]!
    pageInfo: PageInfo
}

interface IProduct {
    sku: String!
    model: ProductModel
    variants: ProductVariantConnection!
}

type ProductAlternative implements IProduct {
    sku: String!
    model: ProductModel
    variants: ProductVariantConnection!
}

type ProductAlternativeEdge {
    node: ProductAlternative!
}

type ProductAlternativeConnection {
    edges: [ProductAlternativeEdge!]!
    pageInfo: PageInfo
}

type Product implements IProduct {
    sku: String!
    model: ProductModel
    variants: ProductVariantConnection!
    alternatives(first: Int): ProductAlternativeConnection!
}

type ProductSet {
    id: String!
    title: String
    description: String
    
    """
    The product for which this product set was requested.
    If this product is currently unavailable the closest 
    alternative will be used.
    """
    triggerProduct: Product!
    
    """
    List of cross-selling products that combine well with 
    the given trigger product.
    """
    setProducts: [Product!]!
}

type ProductSetEdge {
    node: ProductSet!
}

type ProductSetConnection {
    edges: [ProductSetEdge!]!
    pageInfo: PageInfo
}
```

## Introspection Query

Through its introspection capabilities, GraphQL also allows to get information about the underlying schema using [**regular API queries**](https://docs.8select.io/api/general/introduction#how-to-query-graphql). The following example allows to fetch information about all top-level queries, their retrievable fields as well as parameters that can be passed to them:

```graphql
query {
  __schema {
    queryType {
      kind
      name
      fields {
        name
        args {
          name
          type {
            kind
            name
          }
        }
        type {
          fields {
            name
            type {
              kind
              name
            }
          }
        }
      }
    }
  }
}

```

Using appropriate tooling though, it will not be necessary to query this information most of the time. Instead almost every modern development environment has built-in functionalities to provide the information automatically.

