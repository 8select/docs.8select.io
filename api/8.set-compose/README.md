---
description: >-
  Query 8.SET Compose product set by an arbitrary product identifier from your
  catalogue.
---

# 8.SET Compose \(Alpha\)

## Complete product sets by SKU

This example illustrates fetching 8.SET Compose product sets by a given SKU from your catalogue.

{% hint style="warning" %}
Please note that in the example the field is still called `productSets` but will soon be renamed to `setCompose`. For backwards compatibility reasons we will provide both fields for a while.
{% endhint %}

{% tabs %}
{% tab title="GraphQL Query" %}
```graphql
query {
  productSets(input: {queryType: SKU, value: "486890-0001-09900"}, first: 1) {
    edges {
      node {
        id
        title
        description
        triggerProduct {
          alternatives {
            edges {
              node {
                sku
                model {
                  id
                }
                variants {
                  edges {
                    node {
                      sku
                    }
                  }
                }
              }
            }
          }
          model {
            id
          }
          sku
          variants {
            pageInfo {
              endCursor
            }
            edges {
              node {
                sku
              }
            }
          }
        }
        setProducts {
          variants {
            edges {
              node {
                sku
              }
            }
          }
          model {
            id
          }
          alternatives {
            edges {
              node {
                sku
                variants {
                  edges {
                    node {
                      sku
                    }
                  }
                }
              }
            }
          }
          sku
        }
      }
    }
  }
}

```
{% endtab %}

{% tab title="Request" %}
```bash
curl https://api-demo.8select.io/graphql \
-H 'x-api-id: <Your API ID>'  \
-H 'Content-Type: application/json' \
-d '{"query":"query {\n  productSets(input: {queryType: SKU, value: \"486890-0001-09900\"}, first: 1) {\n    edges {\n      node {\n        setProducts {\n          variants {\n            edges {\n              node {\n                sku\n              }\n            }\n          }\n          model {\n            id\n          }\n          alternatives {\n            edges {\n              node {\n                sku\n                variants {\n                  edges {\n                    node {\n                      sku\n                    }\n                  }\n                }\n              }\n            }\n          }\n          sku\n        }\n        description\n        id\n        title\n        triggerProduct {\n          alternatives {\n            edges {\n              node {\n                sku\n                model {\n                  id\n                }\n                variants {\n                  edges {\n                    node {\n                      sku\n                    }\n                  }\n                }\n              }\n            }\n          }\n          model {\n            id\n          }\n          sku\n          variants {\n            pageInfo {\n              endCursor\n            }\n            edges {\n              node {\n                sku\n              }\n            }\n          }\n        }\n      }\n    }\n  }\n}\n"}'
```
{% endtab %}

{% tab title="Response" %}
```javascript
{
  "data": {
    "productSets": {
      "edges": [
        {
          "node": {
            "id": "f0db275c-f7ef-4a2c-8704-f51318c261ba",
            "title": "Steppjacke mit rosa Pullover und dunkelblauer Jeanshose",            
            "description": null,
            "setProducts": [
              {
                "variants": {
                  "edges": [
                    { "node": { "sku": "476006-0002-00480" } },
                    ...
                  ]
                },
                "model": { "id": "476006" },
                "alternatives": {
                  "edges": [
                    {
                      "node": {
                        "sku": "480103-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "480103-0002-09990" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "370625-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "370625-0002-00340" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "483729-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "483729-0002-09990" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "487556-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487556-0001-00480" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "483248-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "483248-0002-09970" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "454810-0004",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "454810-0004-00420" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "484993-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "484993-0002-00480" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "424897-0012",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "424897-0012-00480" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "424897-0008",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "424897-0008-00480" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "502504-0003",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "502504-0003-09960" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "490552-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "490552-0002-00460" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "485626-0003",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "485626-0003-00360" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "424897-0010",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "424897-0010-00480" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "487667-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487667-0001-00360" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "499406-0003",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "499406-0003-09990" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "499407-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "499407-0001-09990" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "487610-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487610-0001-00460" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "486251-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "486251-0001-00400" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "486613-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "486613-0002-09990" } },
                            ...
                          ]
                        }
                      }
                    }
                  ]
                },
                "sku": "476006-0002"
              },
              {
                "variants": {
                  "edges": [
                    { "node": { "sku": "487901-0001-00000" } },
                    ...
                  ]
                },
                "model": { "id": "487901" },
                "alternatives": {
                  "edges": [
                    {
                      "node": {
                        "sku": "487910-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487910-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "476533-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "476533-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "499045-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "499045-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "499044-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "499044-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "437396-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "437396-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "487916-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487916-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "487914-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "487914-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "476520-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "476520-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "495673-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "495673-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "491880-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "491880-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "478720-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "478720-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "478724-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "478724-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "485344-0001-00000",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "485344-0001-00000" } },
                            ...
                          ]
                        }
                      }
                    }
                  ]
                },
                "sku": "487901-0001-00000"
              },
              {
                "variants": {
                  "edges": [
                    { "node": { "sku": "464733-0004-03130" } },
                    ...
                  ]
                },
                "model": { "id": "464733" },
                "alternatives": {
                  "edges": [
                    {
                      "node": {
                        "sku": "481427-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "481427-0001-03032" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "482310-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "482310-0001-00400" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "449249-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "449249-0002-00840" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "481496-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "481496-0001-02734" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "462816-0003",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "462816-0003-00360" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "482955-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "482955-0001-00340" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "497946-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "497946-0001-02729" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "462816-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "462816-0002-00340" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "478831-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "478831-0001-03134" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "482341-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "482341-0001-00400" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "428158-0005",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "428158-0005-00440" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "449250-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "449250-0002-00920" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "486275-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "486275-0002-00180" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "483290-0002",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "483290-0002-00360" } },
                            ...
                          ]
                        }
                      }
                    }
                  ]
                },
                "sku": "464733-0004"
              },
              {
                "variants": {
                  "edges": [
                    { "node": { "sku": "423883-0001-00360" } },
                    ...
                  ]
                },
                "model": { "id": "423883" },
                "alternatives": {
                  "edges": [
                    {
                      "node": {
                        "sku": "476108-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "476108-0001-00070" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "462285-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "462285-0001-00410" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "496807-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "496807-0001-00400" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "457603-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "457603-0001-00075" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "492730-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "492730-0001-00410" } },
                            ...
                          ]
                        }
                      }
                    },
                    {
                      "node": {
                        "sku": "492760-0001",
                        "variants": {
                          "edges": [
                            { "node": { "sku": "492760-0001-00410" } },
                            ...
                          ]
                        }
                      }
                    }
                  ]
                },
                "sku": "423883-0001"
              }
            ],
            "triggerProduct": {
              "alternatives": {
                "edges": [
                  {
                    "node": {
                      "sku": "490124-0001",
                      "model": { "id": "490124" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "490124-0001-00460" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "479051-0004",
                      "model": { "id": "479051" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "479051-0004-00460" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "509967-0001",
                      "model": { "id": "509967" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "509967-0001-00480" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "402219-0002",
                      "model": { "id": "402219" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "402219-0002-09970" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "488362-0002",
                      "model": { "id": "488362" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "488362-0002-09970" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "489632-0006",
                      "model": { "id": "489632" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "489632-0006-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "107796-0004",
                      "model": { "id": "107796" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "107796-0004-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "477159-0002",
                      "model": { "id": "477159" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "477159-0002-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "477158-0001",
                      "model": { "id": "477158" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "477158-0001-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "491035-0003",
                      "model": { "id": "491035" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "491035-0003-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "484653-0006",
                      "model": { "id": "484653" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "484653-0006-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "479082-0003",
                      "model": { "id": "479082" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "479082-0003-00420" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "497885-0002",
                      "model": { "id": "497885" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "497885-0002-09960" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "475188-0006",
                      "model": { "id": "475188" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "475188-0006-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "490978-0001",
                      "model": { "id": "490978" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "490978-0001-00420" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "486259-0001",
                      "model": { "id": "486259" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "486259-0001-00360" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "407031-0016",
                      "model": { "id": "407031" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "407031-0016-09990" } },
                          ...
                        ]
                      }
                    }
                  },
                  {
                    "node": {
                      "sku": "510016-0001",
                      "model": { "id": "510016" },
                      "variants": {
                        "edges": [
                          { "node": { "sku": "510016-0001-00460" } },
                          ...
                        ]
                      }
                    }
                  }
                ]
              },
              "model": { "id": "442185" },
              "sku": "442185-0008",
              "variants": {
                "pageInfo": null,
                "edges": [
                  { "node": { "sku": "442185-0008-09990" } },
                  ...
                ]
              }
            }
          }
        }
      ]
    }
  }
}

```
{% endtab %}
{% endtabs %}



