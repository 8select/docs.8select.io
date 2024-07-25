---
description: >-
  Whenever two objects have a one-to-many relationship, the respective field
  will be paginated using cursor-based, forward pagination.
---

# Pagination

{% hint style="warning" %}
As pagination is not yet fully implemented, all paginated fields will allow you to limit the returned items via the first argument. However it is not possible to set an offset.

To avoid breaking changes once pagination will be enabled, the respective pattern is already prepared and enforced.
{% endhint %}

## Nodes and Edges

Objects that share a relationship within our API are referred to as **nodes** and their connections as **edges**. To enable pagination, a field representing a one-to-many relationship contains a single `edges` object, which in turn is a list of nodes. Each such `node` object represents a single related item.

According to this structure, you could query a list of similar products:

```graphql
product(id: "8S-DEMO-Polohemd-1") {
   similarProducts {
      edges {
        node {
          id
        }
      }
    }
  }
}
```

The responding result will reflect the same structure:

<pre class="language-json"><code class="lang-json"><strong>{
</strong>  "data": {
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
          ...,
          {
            "node": {
              "id": "8S-DEMO-Polohemd-6"
            }
          }
        ]
      }
    }
  }
}
</code></pre>

## Slicing

An optional parameter `first` can be used to limit the number of items returned in a result list.&#x20;

The following query for example, would allow you to return only a single 8.SET Compose product set for a product with the SKU `123456-7890` in your catalogue:

```graphql
product(id: "8S-DEMO-Polohemd-1") {
   similarProducts(first: 2) {
      edges {
        node {
          id
        }
      }
    }
  }
}
```

You can pass an arbitrary positive integer to the `first` argument. Bear in mind though, that the result will always be the same shape, even if you request a single item. So the above query would result in:

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
          }
        ]
      }
    }
  }
}
```
