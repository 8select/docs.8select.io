# Einleitung

Voraussetzung für die Befüllung der Widgets mit Inhalten ist eine Anlieferung der Produktdaten des Online-Shops an 8select.

Die Produktdaten werden dabei über eine vom Shop bereitgestellte API abgefragt.

![](../.gitbook/assets/schema.jpg)

## Format

* Im Export sind ausschließlich **Produktvarianten** enthalten.
* Produkteigenschaften die Varianten ausmachen, müssen entsprechend gekennzeichnet sein, zum Beispiel Farbe und Größe. 
* Hat eine Eigenschaft mehrere Werte, so sind die Werte in einem `array` aufzulisten. Zum Beispiel für ein Mehrfarbiges T-Shirt.
* Ein Produkt ist vom Typ `object` und hat 1 bis n `properties`
  * Es gibt Pflichtfelder damit ein Produkt und sein Elternprodukt eindeutig identifizierbar sind
  * Alle Eigenschaften sind vom Typ `object`
    * der `key` einer Eigenschaft ist ein eindeutiger Identifikator
    * `label` - Typ `string` - ein für Menschen lesbarer Bezeichner der Eigenschaft
    * `value` - ist vom Typ `string`, `number`, `string[]` , `number[]`, `boolean`
    * `value` - ist der Wert der Eigenschaft
    * `isVariantDetail` - Typ `boolean`
    * `isVariantDetail` - ist `true` wenn eine Eigenschaft für die Variantenbildung verantwortlich ist, z.B. Farben oder Größen
    * `isVariantDetail`wird nur benötigt wenn der Wert `true` ist, ansonsten kann die Eigenschaft weggelassen werden

### Beispiel Produkt

```javascript
{
  "s_articles_details.id": {
    "label": "id",
    "value": "732"
  },
  "s_articles_details.articleID": {
    "label": "parentId",
    "value": "5"
  },
  "s_articles_details.ordernumber": {
    "label": "Artikelnummer",
    "value": "SW10005.2"
  },
  "url": {
    "label": "URL",
    "value": "http://shopware-5-2-17-php7.staging.8select.io/hoehenluft-abenteuer/ausruestung/zubehoer/stoecke/5/hot-shot-s?number=SW10005.2"
  },
  "images": {
    "label": "Bilder",
    "value": [
      "http://shopware-5-2-17-php7.staging.8select.io/media/image/fd/6c/be/SW10005.jpg",
      "http://shopware-5-2-17-php7.staging.8select.io/media/image/e5/d5/8a/SW10005_1.jpg"
    ]
  },
  "s_articles.name": {
    "label": "Artikel-Bezeichnung",
    "value": "HOT SHOT S"
  },
  "s_articles_supplier.name": {
    "label": "Hersteller",
    "value": "LEKI"
  }
}
```

