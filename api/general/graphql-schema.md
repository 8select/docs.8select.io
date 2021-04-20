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

