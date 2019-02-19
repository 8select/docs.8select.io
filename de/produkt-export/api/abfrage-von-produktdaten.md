# Abfrage von Produktdaten

Die 8select CSE fragt regelmässig die Produktdaten im Shop über die vom Plugin bereitgestellte API ab.

## **Request**

```text
GET /products?limit=\<limit>&offset=\<offset>&delta=\<delta\>&fields[]=\<field-name-1\>&fields[]=\<field-name-2\>&fields[]=\<field-name-3\>
```

### **Parameter**

| name | beschreibung | beispiel |
| :--- | :--- | :--- |
| limit | anzahl von produkten die zurückgegeben werden | `50` |
| offset | abfrage für die produkte überspringt die gegebene anzahl an produkten | `0` |
| delta | nur produkte die sich seit dem letzten request geändert haben | `true`\|`false` |
| fields\[\] | wenn die zurückgegebenen Produkteigenschaften eingeschränkt werden sollen, eine liste von details die zurück gegeben werden sollen | `fields[]=table.with.price.column&fields[]=table.with.rsp.column&fields[]=table.with.stock.column` |

### **Response**

**`HTTP 200`**

```text
{
  "limit": 50,
  "offset": 0,
  "total": 2345,
  "data": [
    {
        "sku": "grand-c-max-2015-race-rot-125-3tz4uiu564z",
        "table.with.sku.column": {
            "label": "sku",
            "value": "grand-c-max-2015-race-rot-125-3tz4uiu564z"
        },
        "table.with.color.column": {
            "label": "Farbe",
            "value": "Race-Rot",
            "isVariantDetail": true
        },
        "table.with.brand.column": {
            "label": "Marke",
            "value": "FORD"
        },
        "table.with.ps.column": {
            "label": "PS",
            "value": 125,
            "isVariantDetail": true
        },
        "table.with.seat_color.column": {
            "label": "Sitzfarbe",
            "value": "schwarz"
        },
        "table.with.mirror_color.column": {
            "label": "Spiegelfarbe",
            "value": "Iridium-Schwarz Mica"
        },
        "table.with.price.column": {
            "label": "Preis",
            "value": 1990000
        },
        "table.with.rsp.column": {
            "label": "UVP",
            "value": 2220000
        },
        "table.with.stock.column": {
            "label": "Bestand",
            "value": 42
        }
    }
  ]
}
```

### **Fehler**

**`HTTP 4xx,5xx`**

```text
{
  "error": "",
  "message": ""
}
```

