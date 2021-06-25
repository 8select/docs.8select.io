# Event Validation

Incoming analytics events are validated before they are accepted and processed. If you encounter any errors during the integration of 8.API Tracking in your product, you can check the structure of your events against our validation test endpoint at `https://api.8select.io/analytics/v3/events/validate`:

```bash
POST /analytics/v3/events/validate
Host: https://api.8select.io
Content-Type: application/json
x-api-id: <Your API ID>

{ 
	"type": "view",

	"view": {
		"type": "setCompose",
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

The above event is missing the `setCompose` property, which is required for `view` events of type `"setCompose"`. The validation endpoint will thus among others report this violation:

```javascript
[
  ...,
  {
    "instancePath": "/view",
    "schemaPath": "#/definitions/PayloadSetCompose/required",
    "keyword": "required",
    "params": {
      "missingProperty": "setCompose"
    },
    "message": "must have required property 'setCompose'"
  },
  ...
]
```

{% hint style="warning" %}
Please note, that the validation endpoint is currently set to be very verbose. This means, it will try to match incoming events against all possible event types. The reported schema violations will thus include additional alerts regarding the allowed values of the top-level `type` property. These can be disregarded for now and we are working on a solution to make the output easier to interpret.
{% endhint %}

If you are familiar with JSON Schema, you can also validate your event structure against the following full schema declaration:

```javascript
{
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://json-schema.org/draft-07/schema#",
  "title": "8.LYTICS v3 Tracking Event Schema",
  "allOf": [
    {
      "oneOf": [
        {
          "$ref": "#/definitions/EventApi"
        },
        {
          "$ref": "#/definitions/EventInteract"
        },
        {
          "$ref": "#/definitions/EventOrder"
        },
        {
          "$ref": "#/definitions/EventView"
        }
      ]
    },
    {
      "properties": {
        "context": {
          "$ref": "#/definitions/Context"
        }
      },
      "required": [
        "context"
      ],
      "type": "object"
    }
  ],
  "definitions": {
    "Context": {
      "contains": {
        "$ref": "#/definitions/ContextUser"
      },
      "items": {
        "oneOf": [
          {
            "$ref": "#/definitions/ContextContent"
          },
          {
            "$ref": "#/definitions/ContextWidget"
          },
          {
            "$ref": "#/definitions/ContextPage"
          },
          {
            "$ref": "#/definitions/ContextApi"
          },
          {
            "$ref": "#/definitions/ContextSession"
          },
          {
            "$ref": "#/definitions/ContextUser"
          }
        ]
      },
      "type": "array",
      "uniqueItems": true
    },
    "ContextApi": {
      "additionalProperties": false,
      "properties": {
        "api": {
          "additionalProperties": false,
          "properties": {
            "id": {
              "type": "string"
            },
            "sourceIp": {
              "type": "string"
            },
            "userAgent": {
              "type": "string"
            }
          },
          "required": [
            "id"
          ],
          "type": "object"
        },
        "type": {
          "enum": [
            "api"
          ],
          "type": "string"
        }
      },
      "required": [
        "api",
        "type"
      ],
      "type": "object"
    },
    "ContextContent": {
      "additionalProperties": false,
      "properties": {
        "content": {
          "additionalProperties": false,
          "properties": {
            "id": {
              "type": "string"
            }
          },
          "required": [
            "id"
          ],
          "type": "object"
        },
        "type": {
          "enum": [
            "content"
          ],
          "type": "string"
        }
      },
      "required": [
        "content",
        "type"
      ],
      "type": "object"
    },
    "ContextPage": {
      "additionalProperties": false,
      "properties": {
        "page": {
          "additionalProperties": false,
          "properties": {
            "url": {
              "type": "string"
            }
          },
          "required": [
            "url"
          ],
          "type": "object"
        },
        "type": {
          "enum": [
            "page"
          ],
          "type": "string"
        }
      },
      "required": [
        "page",
        "type"
      ],
      "type": "object"
    },
    "ContextSession": {
      "additionalProperties": false,
      "properties": {
        "session": {
          "additionalProperties": false,
          "properties": {
            "id": {
              "type": "string"
            }
          },
          "required": [
            "id"
          ],
          "type": "object"
        },
        "type": {
          "enum": [
            "session"
          ],
          "type": "string"
        }
      },
      "required": [
        "session",
        "type"
      ],
      "type": "object"
    },
    "ContextUser": {
      "additionalProperties": false,
      "properties": {
        "type": {
          "enum": [
            "user"
          ],
          "type": "string"
        },
        "user": {
          "additionalProperties": false,
          "properties": {
            "id": {
              "type": "string"
            }
          },
          "required": [
            "id"
          ],
          "type": "object"
        }
      },
      "required": [
        "type",
        "user"
      ],
      "type": "object"
    },
    "ContextWidget": {
      "additionalProperties": false,
      "properties": {
        "type": {
          "enum": [
            "widget"
          ],
          "type": "string"
        },
        "widget": {
          "additionalProperties": false,
          "properties": {
            "id": {
              "type": "string"
            },
            "type": {
              "type": "string"
            }
          },
          "required": [
            "id",
            "type"
          ],
          "type": "object"
        }
      },
      "required": [
        "type",
        "widget"
      ],
      "type": "object"
    },
    "CurrencyCode": {
      "enum": [
        "AED",
        "AFN",
        "ALL",
        "AMD",
        "ANG",
        "AOA",
        "ARS",
        "AUD",
        "AWG",
        "AZN",
        "BAM",
        "BBD",
        "BDT",
        "BGN",
        "BHD",
        "BIF",
        "BMD",
        "BND",
        "BOB",
        "BRL",
        "BSD",
        "BTN",
        "BWP",
        "BYR",
        "BZD",
        "CAD",
        "CDF",
        "CHF",
        "CLP",
        "CNY",
        "COP",
        "CRC",
        "CUC",
        "CUP",
        "CVE",
        "CZK",
        "DJF",
        "DKK",
        "DOP",
        "DZD",
        "EGP",
        "ERN",
        "ETB",
        "EUR",
        "FJD",
        "FKP",
        "GBP",
        "GEL",
        "GGP",
        "GHS",
        "GIP",
        "GMD",
        "GNF",
        "GTQ",
        "GYD",
        "HKD",
        "HNL",
        "HRK",
        "HTG",
        "HUF",
        "IDR",
        "ILS",
        "IMP",
        "INR",
        "IQD",
        "IRR",
        "ISK",
        "JEP",
        "JMD",
        "JOD",
        "JPY",
        "KES",
        "KGS",
        "KHR",
        "KMF",
        "KPW",
        "KRW",
        "KWD",
        "KYD",
        "KZT",
        "LAK",
        "LBP",
        "LKR",
        "LRD",
        "LSL",
        "LYD",
        "MAD",
        "MDL",
        "MGA",
        "MKD",
        "MMK",
        "MNT",
        "MOP",
        "MRO",
        "MUR",
        "MVR",
        "MWK",
        "MXN",
        "MYR",
        "MZN",
        "NAD",
        "NGN",
        "NIO",
        "NOK",
        "NPR",
        "NZD",
        "OMR",
        "PAB",
        "PEN",
        "PGK",
        "PHP",
        "PKR",
        "PLN",
        "PYG",
        "QAR",
        "RON",
        "RSD",
        "RUB",
        "RWF",
        "SAR",
        "SBD",
        "SCR",
        "SDG",
        "SEK",
        "SGD",
        "SHP",
        "SLL",
        "SOS",
        "SPL",
        "SRD",
        "STD",
        "SVC",
        "SYP",
        "SZL",
        "THB",
        "TJS",
        "TMT",
        "TND",
        "TOP",
        "TRY",
        "TTD",
        "TVD",
        "TWD",
        "TZS",
        "UAH",
        "UGX",
        "USD",
        "UYU",
        "UZS",
        "VEF",
        "VND",
        "VUV",
        "WST",
        "XAF",
        "XCD",
        "XDR",
        "XOF",
        "XPF",
        "YER",
        "ZAR",
        "ZMW",
        "ZWD"
      ],
      "type": "string"
    },
    "EventApi": {
      "properties": {
        "api": {
          "allOf": [
            {
              "oneOf": [
                {
                  "$ref": "#/definitions/PayloadSetCompose"
                }
              ]
            },
            {
              "additionalProperties": false,
              "properties": {
                "action": {
                  "enum": [
                    "query"
                  ],
                  "type": "string"
                },
                "arguments": {
                  "type": "object"
                }
              },
              "required": [
                "action"
              ],
              "type": "object"
            }
          ]
        },
        "type": {
          "enum": [
            "api"
          ],
          "type": "string"
        }
      },
      "required": [
        "api",
        "type"
      ],
      "type": "object"
    },
    "EventInteract": {
      "properties": {
        "interact": {
          "allOf": [
            {
              "oneOf": [
                {
                  "$ref": "#/definitions/PayloadProduct"
                }
              ]
            },
            {
              "additionalProperties": false,
              "properties": {
                "action": {}
              },
              "type": "object"
            }
          ]
        },
        "type": {
          "enum": [
            "interact"
          ],
          "type": "string"
        }
      },
      "required": [
        "interact",
        "type"
      ],
      "type": "object"
    },
    "EventOrder": {
      "properties": {
        "order": {
          "$ref": "#/definitions/PayloadOrder"
        },
        "type": {
          "enum": [
            "order"
          ],
          "type": "string"
        }
      },
      "required": [
        "order",
        "type"
      ],
      "type": "object"
    },
    "EventView": {
      "properties": {
        "type": {
          "enum": [
            "view"
          ],
          "type": "string"
        },
        "view": {
          "oneOf": [
            {
              "$ref": "#/definitions/PayloadSetCompose"
            }
          ]
        }
      },
      "required": [
        "type",
        "view"
      ],
      "type": "object"
    },
    "PayloadOrder": {
      "additionalProperties": false,
      "properties": {
        "id": {
          "type": "string"
        },
        "lines": {
          "items": {
            "additionalProperties": false,
            "properties": {
              "grossPrice": {
                "additionalProperties": false,
                "properties": {
                  "amount": {
                    "type": "number"
                  },
                  "currency": {
                    "$ref": "#/definitions/CurrencyCode"
                  }
                },
                "required": [
                  "amount",
                  "currency"
                ],
                "type": "object"
              },
              "quantity": {
                "type": "number"
              },
              "sku": {
                "type": "string"
              }
            },
            "required": [
              "grossPrice",
              "quantity",
              "sku"
            ],
            "type": "object"
          },
          "type": "array"
        }
      },
      "required": [
        "id",
        "lines"
      ],
      "type": "object"
    },
    "PayloadProduct": {
      "additionalProperties": false,
      "properties": {
        "product": {
          "additionalProperties": false,
          "properties": {
            "sku": {
              "type": "string"
            }
          },
          "required": [
            "sku"
          ],
          "type": "object"
        },
        "type": {
          "enum": [
            "product"
          ],
          "type": "string"
        }
      },
      "required": [
        "product",
        "type"
      ],
      "type": "object"
    },
    "PayloadSetCompose": {
      "additionalProperties": false,
      "properties": {
        "setCompose": {
          "anyOf": [
            {
              "additionalProperties": false,
              "properties": {
                "id": {
                  "type": "string"
                }
              },
              "required": [
                "id"
              ],
              "type": "object"
            },
            {
              "type": "null"
            }
          ]
        },
        "type": {
          "enum": [
            "setCompose"
          ],
          "type": "string"
        }
      },
      "required": [
        "type",
        "setCompose"
      ],
      "type": "object"
    }
  }
}
```

