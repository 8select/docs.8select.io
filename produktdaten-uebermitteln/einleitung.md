# Einleitung

Voraussetzung für die Befüllung der Widgets mit Inhalten ist eine Anlieferung der Produktdaten des Online-Shops an 8select.

Die Produktdaten werden dabei über eine vom Shop bereitgestellte API abgefragt.

![](../.gitbook/assets/schema.jpg)

## Format

* Im Export sind ausschließlich Produktvarianten enthalten.
* Produkteigenschaften die Varianten ausmachen, müssen entsprechend gekennzeichnet sein, zum Beispiel Farbe und Größe. 
* Hat eine Eigenschaft mehrere Werte, so sind die Werte in einem `array` aufzulisten. Zum Beispiel für ein Mehrfarbiges T-Shirt.
* Ein Produkt ist vom Typ `object` und hat 1 bis n `properties`
  * Identifikator für ein Produkt ist die `property` mit dem Bezeichner `sku` vom Typ `string` 
  * Alle weiteren Eigenschaften sind wiederum vom Typ `object`
    * der `key` einer Eigenschaft ist ein eindeutiger Identifikator
    * `label` - Typ `string` - ein für Menschen lesbarer Bezeichner der Eigenschaft
    * `value` - ist vom Typ `string`, `number`, `array<string>` oder `array<number>`
    * `value` - ist der Wert der Eigenschaft
    * `isVariantDetail` - Typ `boolean`
    * `isVariantDetail` - ist `true` wenn eine Eigenschaft für die Variantenbildung verantwortlich ist, z.B. Farben oder Größen

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

