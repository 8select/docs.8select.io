---
description: Full annotated GraphQL introspection schema for reference.
---

# GraphQL Schema

```graphql
schema {
  query: Query
}

"""
The 8SELECT GraphQL API currently supports 8.SET Compose only.
"""
type Query {
  """
  @deprecated
  Fetch 8.SET Compose product sets for a given trigger product.
  """
  productSets(
    "Specifies the trigger product for which to fetch product sets."
    input: SetComposeQueryInput!
    "An optional number of product sets to fetch."
    first: Int
  ): ProductSetConnection
    @deprecated(reason: "Please use `setCompose` query instead.")

  """
  Fetch 8.SET Compose product sets for a given trigger product.
  """
  setCompose(
    "Specifies the trigger product for which to fetch product sets."
    input: SetComposeQueryInput!
    "An optional number of product sets to fetch."
    first: Int
  ): ProductSetConnection

  """
  Fetch 8.SET Photo sets
  """
  setPhoto(
    input: SetPhotoQueryInput
    "The end cursor of the previous page of photo sets"
    after: String
    "An optional number of photo sets to fetch (default: 10)."
    first: Int
  ): PhotoSetConnection
}

"""
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
The trigger product for which to query product sets.
"""
input SetComposeQueryInput {
  "The type of identifier by which to specify the trigger product."
  queryType: SetComposeQueryType!
  "The actual identifier to which the `queryType` refers."
  value: String!
}

"""
The set of query types supported by `setPhoto`.
"""
enum SetPhotoQueryType {
  "The identifier for photo set tags."
  TAGS
}

"""
The photo set filter values which to include and exclude.
If the queryType 'TAGS' is set. either include or exclude must contain at least one item
"""
input SetPhotoQueryInputTagFilter {
  "The filter values which to exclude."
  exclude: [String!]!
  "The filter values which to include."
  include: [String!]!
}

"""
The photo set filters with which the photo sets are queried.
"""
input SetPhotoQueryInput {
  "The type of identifier by which to filter the photo sets."
  queryType: SetPhotoQueryType!
  "The actual filter values to which the `queryType` refers."
  value: SetPhotoQueryInputTagFilter!
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
A "page" of product sets containg a given number of items.
"""
type ProductSetConnection {
  "The list of product sets in the current page."
  edges: [ProductSetEdge!]!
  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
A "page" of photo sets containing a given number of items
"""
type PhotoSetConnection {
  "The list of photo sets in the current page."
  edges: [PhotoSetEdge!]!
  pageInfo: PageInfo!
}

"""
An edge referring to a single product set.
"""
type ProductSetEdge {
  "The product set this edge refers to."
  node: ProductSet!
}

"""
An edge referring to a single photo set.
"""
type PhotoSetEdge {
  "The photo set this edge refers to."
  node: PhotoSet!
}

"""
A product set based on a given trigger product.
"""
type ProductSet {
  "The id of this specific product set."
  id: String!
  "The id of the snapshot for the specific product set used in this API request."
  snapshotId: String
  "An optional title of the product set."
  title: String
  "An optional description of the product set."
  description: String
  """
  The trigger product this product set is based upon.
  _Note: If this product is currently unavailable the closest alternative will
  be used._
  """
  triggerProduct: Product!
  """
  List of cross-selling products that combine well with the trigger product.
  """
  setProducts: [Product!]!
}

"""
A photo set based on a given filter
"""
type PhotoSet {
  "The id of this specific photo set."
  id: String!
  "An optional title of the photo set."
  title: String
  "The list of images of the current photo set."
  images: PhotoSetImageConnection!
  tags: [String!]
}

"""
A "page" of photo set images
"""
type PhotoSetImageConnection {
  "The list of photo set images of the current photo set."
  edges: [PhotoSetImageEdge!]!
}

"""
An edge referring to a single image of a specific photo set
"""
type PhotoSetImageEdge {
  "The photo set image this edge refers to."
  node: PhotoSetImage!
}

"""
An image of a specific photo set
"""
type PhotoSetImage {
  "The image url of a photo set"
  url: String!
}

"""
The interface of fields all product types have in common.
"""
interface IProduct {
  "The stock keeping unit of a product."
  sku: String!
  "The model a product is based upon."
  model: ProductModel
  "A list of variants for a product."
  variants: ProductVariantConnection!
}

"""
A specific product.
"""
type Product implements IProduct {
  "The stock keeping unit of this product."
  sku: String!
  "The model this product is based upon."
  model: ProductModel
  "The list of variants for this product."
  variants: ProductVariantConnection!
  """
  The list of similar products to potentially substitute this product with in
  a product set.
  """
  alternatives(first: Int): ProductAlternativeConnection!
}

"""
A "page" of alternative products containing a given number of items.
"""
type ProductAlternativeConnection {
  "The list of similar products in the current page."
  edges: [ProductAlternativeEdge!]!
  "The pagination information of the current page."
  pageInfo: PageInfo
}

"""
An edge referring to a single alternative product.
"""
type ProductAlternativeEdge {
  "The alternative product this edge refers to."
  node: ProductAlternative!
}

"""
A specific alternative product.
"""
type ProductAlternative implements IProduct {
  "The stock keeping unit of this product."
  sku: String!
  "The model this product is based upon."
  model: ProductModel
  "The list of variants for this product."
  variants: ProductVariantConnection!
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
  "The stock keeping unit referring to this specific product variant."
  sku: String!
}

"""
A model uniting several products.
"""
type ProductModel {
  id: String!
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
