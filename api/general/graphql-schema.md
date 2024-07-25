---
description: Full annotated GraphQL introspection schema for reference.
---

# GraphQL Schema

```graphql
schema {
  query: Query
}

type Query {
  """
  Retrieves a single custom set by its id.
  """
  customSet(id: ID!): CustomSet

  """
  References a product by id, which exposes fields for cluster sets,
  custom sets and similar products. `id` can be a SKU or main SKU.
  """
  product(id: ID!): ProductReference

  """
  @deprecated
  Fetch 8.SET Compose product sets for a given trigger product.
  """
  setCompose(
    "An optional number of product sets to fetch."
    first: Int
    "Specifies the trigger product for which to fetch product sets."
    input: SetComposeQueryInput!
  ): SetComposeConnection
    @deprecated(
      reason: "Please use `matchingProductClusters` field on `product` query instead."
    )
}

type CustomSetConnection {
  "The list of custom sets in the current page."
  edges: [CustomSetEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

type CustomSetEdge {
  "The custom set this edge refers to."
  node: CustomSet!
}

type CustomSet {
  "An optional description."
  description: String

  "The id of this specific product set."
  id: ID!

  "The list of images of the set. May be empty."
  images(first: Int): ImageConnection!

  "List of products in order of definition."
  products: [CustomSetProduct!]!

  "The list of tags of the set. May be empty."
  tags: [String!]!

  "An optional title."
  title: String
}

type ImageConnection {
  "The list of custom sets in the current page."
  edges: [ImageEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

type ImageEdge {
  "The custom set this edge refers to."
  node: Image!
}

type Image {
  "The url of the image"
  url: String!
}

type ProductReference {
  customSets(
    "An optional number of sets to fetch (default: 1)."
    first: Int
  ): CustomSetConnection

  matchingProductClusters(
    "An optional number of product clusters to fetch (default: 5)."
    first: Int
  ): ProductClusterConnection

  similarProducts(
    "An optional number of products to fetch (default: 12)."
    first: Int
  ): ProductConnection
}

type ProductClusterConnection {
  "The list of clusters in the current page."
  edges: [ProductClusterEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

type ProductClusterEdge {
  "The cluster this edge refers to."
  node: ProductCluster!
}

type ProductCluster {
  "The id of this specific cluster."
  id: ID!

  """
  List of products contained in this cluster. Products are sorted by their
  likelihood of conversion.
  """
  products(
    "An optional number of products to fetch (default: 12)."
    first: Int
  ): ProductConnection!
}

interface IProduct {
  "The brand of this product."
  brand: String

  "The id of this product."
  id: ID!

  "The list of images of the product. May be empty."
  images: ImageConnection!

  "The model this product is based upon."
  modelId: String

  "The name of this product."
  name: String!

  "A list of tags attached to this product."
  tags: [String!]!

  "The online store URL of this product."
  url: String!

  "The list of variants for this product."
  variants(first: Int): ProductVariantConnection!
}

type ProductConnection {
  "The list of custom sets in the current page."
  edges: [ProductEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

type ProductEdge {
  "The custom set this edge refers to."
  node: Product!
}

type Product implements IProduct {
  "The brand of this product."
  brand: String

  "The id of this product."
  id: ID!

  "The list of images of the product. May be empty."
  images: ImageConnection!

  "The model this product is based upon."
  modelId: String

  "The name of this product."
  name: String!

  "A list of tags attached to this product."
  tags: [String!]!

  "The online store URL of this product."
  url: String!

  "The list of variants for this product."
  variants(first: Int): ProductVariantConnection!
}

type CustomSetProduct implements IProduct {
  "The brand of this product."
  brand: String

  "The id of this product."
  id: ID!

  "The list of images of the product. May be empty."
  images: ImageConnection!

  "The model this product is based upon."
  modelId: String

  "The name of this product."
  name: String!

  similarProducts(
    "An optional number of products to fetch (default: 12)."
    first: Int
  ): ProductConnection

  "A list of tags attached to this product."
  tags: [String!]!

  "The online store URL of this product."
  url: String!

  "The list of variants for this product."
  variants(first: Int): ProductVariantConnection!
}

"""
A "page" of product variants containing a given number of items.
"""
type ProductVariantConnection {
  "The list of product variants in the current page."
  edges: [ProductVariantEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
An edge referring to a single product variant.
"""
type ProductVariantEdge {
  "The product variant this edge refers to."
  node: ProductVariant!
}

"""
The specific variant of a product.
"""
type ProductVariant {
  "The id referring to this specific product variant."
  id: ID!

  "The manufacturer's suggested retail price."
  manufacturerSuggestedRetailPrice: Price

  "The price of this product variant."
  price: Price!
}

enum CurrencyCode {
  "Euro (EUR)"
  EUR

  "Polish Zlotych (PLN)"
  PLN

  "United States Dollars (USD)"
  USD
}

type Price {
  """
  The decimal amount of the price, e.g "19.99".
  """
  amount: String!

  "The currency of the price."
  currencyCode: CurrencyCode!
}

"""
The pagination information of the current page.
"""
type PageInfo {
  "The cursor identifying the end of the current page."
  endCursor: String

  "Indicates whether more data is available"
  hasNextPage: Boolean!
}

"""
@deprecated
The set of query types supported by `setCompose`.
"""
enum SetComposeQueryType {
  "The stock keeping unit identifier for a set of different product variants."
  MAIN_SKU
  "The identifier specifying a set of different products of the same model."
  MODEL_ID
  "The stock keeping unit identifier for a specific product."
  SKU
}

"""
@deprecated
The trigger product for which to query product sets.
"""
input SetComposeQueryInput {
  "The type of identifier by which to specify the trigger product."
  queryType: SetComposeQueryType!
  "The actual identifier to which the `queryType` refers."
  value: String!
}

"""
@deprecated
A "page" of product sets containg a given number of items.
"""
type SetComposeConnection {
  "The list of product sets in the current page."
  edges: [SetComposeEdge!]!
  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
@deprecated
An edge referring to a single product set.
"""
type SetComposeEdge {
  "The product set this edge refers to."
  node: SetCompose!
}

"""
@deprecated
A product set based on a given trigger product.
"""
type SetCompose {
  "An optional description of the product set."
  description: String
  "The id of this specific product set."
  id: String!
  "List of cross-selling products that combine well with the trigger product."
  setProducts: [SetComposeProduct!]!
  "The id of the snapshot for the specific product set used in this API request."
  snapshotId: String
  "An optional title of the product set."
  title: String
  """
  The trigger product this product set is based upon.
  _Note: If this product is currently unavailable the closest alternative will
  be used._
  """
  triggerProduct: SetComposeProduct!
}

"""
@deprecated
A specific product.
"""
type SetComposeProduct {
  """
  The list of similar products to potentially substitute this product with in
  a product set. Products are sorted by their likelihood of conversion.
  """
  alternatives(first: Int): SetComposeProductAlternativeConnection!
  "The model this product is based upon."
  model: ProductModel
  "The stock keeping unit of this product."
  sku: String!
  "The list of variants for this product."
  variants: SetComposeProductVariantConnection!
}

"""
@deprecated
A "page" of alternative products containing a given number of items.
"""
type SetComposeProductAlternativeConnection {
  "The list of similar products in the current page."
  edges: [SetComposeProductAlternativeEdge!]!
  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
@deprecated
An edge referring to a single alternative product.
"""
type SetComposeProductAlternativeEdge {
  "The alternative product this edge refers to."
  node: SetComposeProductAlternative!
}

"""
@deprecated
A specific alternative product.
"""
type SetComposeProductAlternative {
  "The model this product is based upon."
  model: ProductModel
  "The stock keeping unit of this product."
  sku: String!
  "The list of variants for this product."
  variants: SetComposeProductVariantConnection!
}

"""
@deprecated
A model uniting several products.
"""
type ProductModel {
  id: String!
}

"""
@deprecated
A "page" of product variants containing a given number of items.
"""
type SetComposeProductVariantConnection {
  "The list of product variants in the current page."
  edges: [SetComposeProductVariantEdge!]!

  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
@deprecated
An edge referring to a single product variant.
"""
type SetComposeProductVariantEdge {
  "The product variant this edge refers to."
  node: SetComposeProductVariant!
}

"""
@deprecated
The specific variant of a product.
"""
type SetComposeProductVariant {
  "The stock keeping unit referring to this specific product variant."
  sku: String!
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
