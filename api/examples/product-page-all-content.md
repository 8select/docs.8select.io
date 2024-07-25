---
description: Fetch all available content for a given product identifier.
---

# Product Page - All Content

## What we want to build

We want to show a custom set, similar products and matching products on our product page.

With the power of GraphQL we can request not only one type of content but all in one query. That way we can fetch all available content with just one HTTP request.

For the matching products we do not want to show similar products for our current product, only other matching categories. So we will request up to 6 `matchingProductClusters` and will skip the first one when we render our UI.

<figure><img src="../../.gitbook/assets/all-content.gif" alt=""><figcaption></figcaption></figure>

## GraphQL query and response

{% tabs %}
{% tab title="GraphQL query" %}
```graphql
query {
  product(id: "8S-DEMO-Polohemd-1") {
    matchingProductClusters(first: 6) {
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
    similarProducts(first: 8) {
      edges {
        node {
          id
        }
      }
    }
    customSets {
      edges {
        node {
          id
          title
          description
          images {
            edges {
              node {
                url
              }
            }
          }
          products {
            id
            similarProducts(first: 2) {
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
}

```
{% endtab %}

{% tab title="cURL request" %}
{% code overflow="wrap" %}
```bash
curl --request POST \
  --url https://api.8select.io/graphql \
  --header 'Content-Type: application/json' \
  --header 'x-api-id: db54750f-80fc-4818-9455-30ca233225dc' \
  --data '{"query":"query {\n  product(id: \"8S-DEMO-Polohemd-1\") {\n    matchingProductClusters(first: 6) {\n      edges {\n        node {\n          products(first: 3) {\n            edges {\n              node {\n                id\n              }\n            }\n          }\n        }\n      }\n    }\n    similarProducts(first: 8) {\n      edges {\n        node {\n          id\n        }\n      }\n    }\n    customSets {\n      edges {\n        node {\n          id\n          title\n          description\n          images {\n            edges {\n              node {\n                url\n              }\n            }\n          }\n          products {\n            id\n            similarProducts(first: 2) {\n              edges {\n                node {\n                  id\n                }\n              }\n            }\n          }\n        }\n      }\n    }\n  }\n}\n"}'
```
{% endcode %}
{% endtab %}

{% tab title="response" %}
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
                  {
                    "node": {
                      "id": "8S-DEMO-Polohemd-10"
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
                  }
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  {
                    "node": {
                      "id": "8S-DEMO-Uhr-1"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Uhr-2"
                    }
                  }
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  {
                    "node": {
                      "id": "8S-DEMO-Gürtel-3"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Gürtel-4"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Gürtel-1"
                    }
                  }
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  {
                    "node": {
                      "id": "8S-DEMO-Hose-1"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Hose-3"
                    }
                  }
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  {
                    "node": {
                      "id": "8S-DEMO-Handschuhe-1"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Handschuhe-2"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Handschuhe-3"
                    }
                  }
                ]
              }
            }
          },
          {
            "node": {
              "products": {
                "edges": [
                  {
                    "node": {
                      "id": "8S-DEMO-Jacket-2"
                    }
                  },
                  {
                    "node": {
                      "id": "8S-DEMO-Jacket-1"
                    }
                  }
                ]
              }
            }
          }
        ]
      },
      "similarProducts": {
        "edges": [
          {
            "node": {
              "id": "8S-DEMO-Polohemd-1"
            }
          },
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
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-3"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-4"
            }
          },
          {
            "node": {
              "id": "8S-DEMO-Polohemd-5"
            }
          }
        ]
      },
      "customSets": {
        "edges": [
          {
            "node": {
              "id": "e3bcaf66-5037-4d7b-be4a-8c571a6fb299",
              "title": "8SELECT Fashion for everyday",
              "description": "This is a demo set. It is here to preview the 8.SET Custom widget.",
              "images": {
                "edges": [
                  {
                    "node": {
                      "url": "https://thumbnails.8scdn.io/9056af8c-e9b8-50db-bdf1-f794dc2e10d7.jpg"
                    }
                  }
                ]
              },
              "products": [
                {
                  "id": "8S-DEMO-Jacket-1",
                  "similarProducts": {
                    "edges": [
                      {
                        "node": {
                          "id": "8S-DEMO-Jacket-2"
                        }
                      }
                    ]
                  }
                },
                {
                  "id": "8S-DEMO-Polohemd-1",
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
                },
                {
                  "id": "8S-DEMO-Gürtel-1",
                  "similarProducts": {
                    "edges": [
                      {
                        "node": {
                          "id": "8S-DEMO-Gürtel-3"
                        }
                      },
                      {
                        "node": {
                          "id": "8S-DEMO-Gürtel-4"
                        }
                      }
                    ]
                  }
                },
                {
                  "id": "8S-DEMO-Hose-1",
                  "similarProducts": {
                    "edges": [
                      {
                        "node": {
                          "id": "8S-DEMO-Hose-2"
                        }
                      },
                      {
                        "node": {
                          "id": "8S-DEMO-Hose-3"
                        }
                      }
                    ]
                  }
                },
                {
                  "id": "8S-DEMO-Schuhe-1",
                  "similarProducts": {
                    "edges": [
                      {
                        "node": {
                          "id": "8S-DEMO-Schuhe-2"
                        }
                      },
                      {
                        "node": {
                          "id": "8S-DEMO-Schuhe-3"
                        }
                      }
                    ]
                  }
                }
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
{% endtabs %}

