# view

A view event should be triggered whenever [**a piece of content slides into the users viewport**](how-to-evaluate-if-view-event-can-be-sent.md). Assuming that you are showing 8.SET-Custom product set data, that event should look like the following example:

```javascript
{
  "type": "view",
  "view": {
    "type": "customSet",
    "setCompose": {
      "id": "1b3de0bd-95c6-435a-8bb9-f4cae0160388"
    }
  },
  "context": [
    {
      "type": "user",
      "user": {
        "id": "c57a43f7-eefc-462b-b5a8-0ef421e90f67"
      }
    }
  ]
}
```

A view event is identified by its type `view` and an additional `view` property containing specific information about the content being viewed. This property should in turn have a type and content-specific payload.

## 8.SIMILAR - similarProducts

A view event with type `similarProducts` must contain a `similarProducts` property containing the `id` of the product the content was requested for.

In our example we request content for `8S-DEMO-Polohemd-1` and also use that as the id in the tracking event.

{% tabs %}
{% tab title="GraphQL query" %}
```graphql
query {
  product(id: "8S-DEMO-Polohemd-1") {
    similarProducts(first: 8) {
      edges {
        node {
          id
        }
      }
    }
  }
}
```
{% endtab %}

{% tab title="GraphQL response" %}
```json
{
  "data": {
    "product": {
      "similarProducts": {
        "edges": [
          ...
        ]
      }
    }
  }
}

```
{% endtab %}

{% tab title="Event payload to send" %}
```json
{ 
  ...,
  "view": {
    "type": "similarProducts",
    "similarProducts": {
      "id": "8S-DEMO-Polohemd-1",
    }
  },
  ...
}
```
{% endtab %}
{% endtabs %}

## 8.SET - matchingProductClusters

A view event with type `matchingProductClusters` must contain a `matchingProductClusters` property containing the `id` of the product the content was requested for.

In our example we request content for `8S-DEMO-Polohemd-1` and also use that as the id in the tracking event.

{% tabs %}
{% tab title="GraphQL query" %}
```graphql
query {
  product(id: "8S-DEMO-Polohemd-1") {
    matchingProductClusters(first: 5) {
      edges {
        node {
          products(first: 3) {
            edges {
              node {
                id
              }
            }
          }
        }
      }
    }
  }
}

```
{% endtab %}

{% tab title="GraphQL response" %}
```json
{
  "data": {
    "product": {
      "matchingProductClusters": {
        "edges": [
          {
            "node": {
              "products": {
                "edges": [
                  ...
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  ...
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  ...
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  ...
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  ...
                ]
              }
            }
          }
        ]
      }
    }
  }
}
```
{% endtab %}

{% tab title="Event payload to send" %}
```json
{ 
  ...,
  "view": {
    "type": "matchingProductClusters",
    "matchingProductClusters": {
      "id": "8S-DEMO-Polohemd-1",
    }
  },
  ...
}
```
{% endtab %}
{% endtabs %}

## 8.SET Custom - customSet

A view event with type `customSet` must contain a `customSet` property containing the `id` of the viewed product set.

The GraphQL API response includes the id of the set depending on the query you use:

* `data.product.customSets.edges[].node.id`
* `data.customSet.id`

{% tabs %}
{% tab title="GraphQL response (product)" %}
```graphql
{
  "data": {
    "product": {
      "customSets": {
        "edges": [
          {
            "node": {
              "id": "e3bcaf66-5037-4d7b-be4a-8c571a6fb299",
              "title": "8SELECT Fashion for everyday",
              "description": "This is a demo set. It is here to preview the 8.SET Custom widget.",
              "images": {
                "edges": [
                  ...
                ]
              },
              "products": [
                ...
              ]
            }
          }
        ]
      }
    }
  }
}
```
{% endtab %}

{% tab title="GraphQL response (customSet)" %}
```graphql
{
  "data": {
    "customSet": {
      "id": "e3bcaf66-5037-4d7b-be4a-8c571a6fb299",
      "title": "8SELECT Fashion for everyday",
      "description": "This is a demo set. It is here to preview the 8.SET Custom widget.",
      "images": {
        "edges": [
          ...
        ]
      },
      "products": [
        ...
      ]
    }
  }
}
```
{% endtab %}

{% tab title="Event payload to send" %}
```json
{ 
  ...,
  "view": {
    "type": "customSet",
    "customSet": {
      "id": "e3bcaf66-5037-4d7b-be4a-8c571a6fb299",
    }
  },
  ...
}
```
{% endtab %}
{% endtabs %}

