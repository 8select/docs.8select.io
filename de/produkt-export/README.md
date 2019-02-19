# produkt-export

Voraussetzung für die Befüllung der Widgets mit Inhalten ist eine Anlieferung der Produktdaten des Online-Shops an 8select.

Die Produktdaten werden dabei über eine vom Shop bereitgestellte API abgefragt.

## Format

* Im Export sind ausschließlich Produktvarianten enthalten.
* Produkteigenschaften die Varianten ausmachen, müssen entsprechend gekennzeichnet sein, zum Beispiel Farbe und Größe. 
* Hat eine Eigenschaft mehrere Werte, so sind die Werte in einem `array` aufzulisten. Zum Beispiel für ein Mehrfarbiges T-Shirt.

### Beispiel Produkt

```javascript
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
  "table.with.material.column": {
    "label": "Material",
    "value": [
        "Aluminium",
        "PVC",
        "Stahl"
    ]
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
```

