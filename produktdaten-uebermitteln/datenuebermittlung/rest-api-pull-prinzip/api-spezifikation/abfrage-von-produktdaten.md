# Abfrage von Produktdaten

{% api-method method="get" host="https://shopware.demo.8select.io" path="/cse-api/products" %}
{% api-method-summary %}
Produktdaten
{% endapi-method-summary %}

{% api-method-description %}
Über den Endpunkt können alle Produktdaten so wie sie im Shop vorkommen abgefragt werden.  
Jeder einzelne Eintrag entspricht dabei einer Produktvariante im Shop.  
  
Um die CSE nutzen zu können, wird ein Mindestdatensatz pro Produkt benötigt.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-query-parameters %}
{% api-method-parameter name="delta" type="boolean" required=false %}
Möglichkeit nur Produkte zurückzugeben die sich seit der letzten Abfrage geändert haben
{% endapi-method-parameter %}

{% api-method-parameter name="fields" type="array" required=false %}
Möglichkeit um die in der Antwort enthaltenen Felder zu limitieren
{% endapi-method-parameter %}

{% api-method-parameter name="limit" type="number" required=false %}
Pagination - Limitierung der in der Antwort enthaltenen Produkte
{% endapi-method-parameter %}

{% api-method-parameter name="offset" type="number" required=false %}
Pagination - Anzahl von Produkten die Übersprungen werden soll
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "limit": 1,
  "offset": 17,
  "total": 677,
  "data": [
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
      },
      "s_articles_details.weight": {
        "label": "Gewicht",
        "value": "0.000"
      },
      "s_articles_details.packunit": {
        "label": "Verpackungseinheit",
        "value": "Paar"
      },
      "s_articles_details.shippingfree": {
        "label": "Versandkostenfrei",
        "value": "0"
      },
      "s_articles.active": {
        "label": "Aktiv für den Hauptartikel",
        "value": "1"
      },
      "s_articles_details.active": {
        "label": "Aktiv für die Variante",
        "value": "1"
      },
      "s_articles.laststock": {
        "label": "Abverkauf",
        "value": "0"
      },
      "s_articles_details.instock": {
        "label": "Lagerbestand",
        "value": "36"
      },
      "s_articles_prices.price": {
        "label": "Brutto-Preis",
        "value": "11995"
      },
      "s_articles_prices.pseudoprice": {
        "label": "Pseudo Brutto-Preis",
        "value": "11995"
      },
      "s_articles_details.isInStock": {
        "label": "Bestellbar",
        "value": "1"
      },
      "s_articles.description_long": {
        "label": "s_articles.description_long",
        "value": "<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Aenean commodo ligula eget dolor. Aenean massa.</p>\n<p>Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Donec quam felis, ultricies nec, pellentesque eu, pretium quis, sem.</p>\n<p>Nulla consequat massa quis enim. Donec pede justo, fringilla vel, aliquet nec, vulputate eget, arcu. In enim justo, rhoncus ut, imperdiet a, venenatis vitae, justo.</p>\n<p>Nullam dictum felis eu pede mollis pretium. Integer tincidunt. Cras dapibus. Vivamus elementum semper nisi. Aenean vulputate eleifend tellus. Aenean leo ligula, porttitor eu, consequat vitae, eleifend ac, enim. Aliquam lorem ante, dapibus in, viverra quis, feugiat.</p>"
      },
      "s_article_configurator_groups.id=5": {
        "label": "Stocklänge",
        "isVariantDetail": true,
        "value": "120 cm"
      },
      "s_filter_options.id=1": {
        "label": "Artikeltyp",
        "value": [
          "Standardkonfigurator",
          "Hervorgehoben",
          "Mit Zubehör-Artikel"
        ]
      },
      "s_filter_options.id=3": {
        "label": "Material",
        "value": "Aluminium"
      },
      "s_filter_options.id=7": {
        "label": "Länge/Größe",
        "value": [
          "120 cm",
          "125 cm",
          "130 cm",
          "135 cm",
          "115 cm",
          "110 cm"
        ]
      },
      "s_filter_options.id=2": {
        "label": "Rohrdurchmesser",
        "value": "16 mm"
      },
      "s_filter_options.id=4": {
        "label": "Gewicht",
        "value": "602 g / Paar"
      },
      "s_filter_options.id=13": {
        "label": "Zielgruppe",
        "value": "Unisex"
      },
      "s_filter_options.id=19": {
        "label": "Einsatzmöglichkeit",
        "value": "Ski"
      },
      "s_categories": {
        "label": "Kategorie",
        "value": [
          "Deutsch",
          "Deutsch > Outdoor & Sports",
          "Deutsch > Outdoor & Sports > Ausrüstung",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör > Stöcke"
        ]
      }
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=403 %}
{% api-method-response-example-description %}
Wenn die API ID oder Feed ID in den Headern nicht mit denen im Shop hinterlegten übereinstimmt.
{% endapi-method-response-example-description %}

```javascript
{
  "error": "AUTH_ERROR",
  "message": "credential mismatch"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Wenn im Request die Header für die Authentifizierung fehlen
{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
Wenn API ID und/oder Feed ID im Shop nicht hinterlegt sind.
{% endapi-method-response-example-description %}

```javascript
{
  "error": "AUTH_ERROR",
  "message": "credentials not configured"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Antwort Format

{% code-tabs %}
{% code-tabs-item title="Root Level" %}
```javascript
{  
  "limit": number // Aktuell gesetztes Limit - Standard kann z.B. 100 sein
  "offset": number // Aktuell gesetztes Offset - Standard ist 0
  "total": number // Gesamtanzahl der Produkte
  "data": array // Die einzelnen Produkte
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Data Level Object Format" %}
```javascript
"name": { string // Identifikator der Produkteigenschaft
  "label": string // Bezeichnung der Produkteigenschaft
  "value": string, string[], number, number[], boolean // Wert(e) der Produkteigenschaft
  "isVariantDetail"?: boolean // Nur vorhanden und true wenn die Produkteigenschaft für die Variantenbildung des Produkts benutzt
}
```
{% endcode-tabs-item %}

{% code-tabs-item title="Data Level Minimum" %}
```javascript
{
  "id": { // Identifikator der Produktvariante
    "label": "id",
    "value": string // Wert - zum Beispiel Datenbank Id
  }
  "parentId": { // Identifikator vom Elternprodukt der Variante
    "label": "parentId",
    "value": string // Wert - zum Beispiel Datenbank Id
  } 
  "sku": { // Stock Keeping Unit der Produktvariante
    "label": "SKU",
    "value": string // Wert
  } 
  "url" { // Deeplink in den Shop die zur Artikeldetailseite führt
    "label": "Deeplink",
    "value": string // URL des Artikels
  }
  "name": { // Name des Produkts
    "label": "Artikel-Bezeichnung",
    "value": string // Wert
  }
  "images": { // Liste von 0 bis n Bildern der Variante
    "label": "Bilder",
    "value": string[] // URLs der Bilder
  }
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Beispiele

#### Mit Filter der Antwort über den Queryparameter `fields` mit nur einem Wert.

{% code-tabs %}
{% code-tabs-item title="API Request - cURL" %}
```bash
curl 'https://shopware.demo.8select.io/cse-api/products?limit=3&offset=18&fields[]=url' \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H '8select-com-fid: 497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H '8select-com-tid: b796a03e-7117-4d12-b40f-e4b06c0ee2dd'

```
{% endcode-tabs-item %}

{% code-tabs-item title="response.json" %}
```javascript
{
  "limit": 3,
  "offset": 18,
  "total": 677,
  "data": [
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "733"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.3"
      },
      "url": {
        "label": "URL",
        "value": "https://shopware.demo.8select.io/hoehenluft-abenteuer/ausruestung/zubehoer/stoecke/5/hot-shot-s?number=SW10005.3"
      }
    },
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "734"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.4"
      },
      "url": {
        "label": "URL",
        "value": "https://shopware.demo.8select.io/hoehenluft-abenteuer/ausruestung/zubehoer/stoecke/5/hot-shot-s?number=SW10005.4"
      }
    },
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "735"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.5"
      },
      "url": {
        "label": "URL",
        "value": "https://shopware.demo.8select.io/hoehenluft-abenteuer/ausruestung/zubehoer/stoecke/5/hot-shot-s?number=SW10005.5"
      }
    }
  ]
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

#### Mit Filter der Antwort über den Queryparameter `fields` mit mehreren Werten.

{% code-tabs %}
{% code-tabs-item title="API Request - cURL" %}
```bash
curl 'https://shopware.demo.8select.io/cse-api/products?limit=1&offset=18&fields[]=s_categories&fields[]=s_article_configurator_groups&fields[]=s_articles_prices.price&fields[]=s_articles_prices.pseudoprice' \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H '8select-com-fid: 497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H '8select-com-tid: b796a03e-7117-4d12-b40f-e4b06c0ee2dd'

```
{% endcode-tabs-item %}

{% code-tabs-item title="response.json" %}
```javascript
{
  "limit": 3,
  "offset": 18,
  "total": 677,
  "data": [
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "733"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.3"
      },
      "s_articles_prices.price": {
        "label": "Brutto-Preis",
        "value": "11995"
      },
      "s_articles_prices.pseudoprice": {
        "label": "Pseudo Brutto-Preis",
        "value": "11995"
      },
      "s_article_configurator_groups.id=5": {
        "label": "Stocklänge",
        "isVariantDetail": true,
        "value": "125 cm"
      },
      "s_categories": {
        "label": "Kategorie",
        "value": [
          "Deutsch",
          "Deutsch > Outdoor & Sports",
          "Deutsch > Outdoor & Sports > Ausrüstung",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör > Stöcke"
        ]
      }
    },
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "734"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.4"
      },
      "s_articles_prices.price": {
        "label": "Brutto-Preis",
        "value": "11995"
      },
      "s_articles_prices.pseudoprice": {
        "label": "Pseudo Brutto-Preis",
        "value": "11995"
      },
      "s_article_configurator_groups.id=5": {
        "label": "Stocklänge",
        "isVariantDetail": true,
        "value": "130 cm"
      },
      "s_categories": {
        "label": "Kategorie",
        "value": [
          "Deutsch",
          "Deutsch > Outdoor & Sports",
          "Deutsch > Outdoor & Sports > Ausrüstung",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör > Stöcke"
        ]
      }
    },
    {
      "s_articles_details.id": {
        "label": "id",
        "value": "735"
      },
      "s_articles_details.articleID": {
        "label": "parentId",
        "value": "5"
      },
      "s_articles_details.ordernumber": {
        "label": "Artikelnummer",
        "value": "SW10005.5"
      },
      "s_articles_prices.price": {
        "label": "Brutto-Preis",
        "value": "11995"
      },
      "s_articles_prices.pseudoprice": {
        "label": "Pseudo Brutto-Preis",
        "value": "11995"
      },
      "s_article_configurator_groups.id=5": {
        "label": "Stocklänge",
        "isVariantDetail": true,
        "value": "135 cm"
      },
      "s_categories": {
        "label": "Kategorie",
        "value": [
          "Deutsch",
          "Deutsch > Outdoor & Sports",
          "Deutsch > Outdoor & Sports > Ausrüstung",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör",
          "Deutsch > Outdoor & Sports > Ausrüstung > Zubehör > Stöcke"
        ]
      }
    }
  ]
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

