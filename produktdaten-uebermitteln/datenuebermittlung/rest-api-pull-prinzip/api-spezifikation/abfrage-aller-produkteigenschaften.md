# Abfrage aller Produkteigenschaften

{% api-method method="get" host="https://shopware.demo.8select.io" path="/cse-api/attributes" %}
{% api-method-summary %}
verfügbare Produkteigenschaften
{% endapi-method-summary %}

{% api-method-description %}
Über den Endpunkt können alle im Shop vorkommenden Produkteigenschaften abgefragt werden.  
Es werden lediglich die Identifikatoren und Bezeichnungen der Eigenschaften zurückgegeben.  
Mit Hilfe der Identifikatoren kann bei der Abfrage von Produkten über den Endpunkt `/products` als Filter die Rückgabe auf vorgegebene Felder via `fields[]` eingeschränkt werden.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "limit": 51,
  "offset": 0,
  "total": 51,
  "data": [
    {
      "name": "s_articles.name",
      "label": "Artikel-Bezeichnung"
    },
    {
      "name": "s_articles.metaTitle",
      "label": "Titel"
    },
    {
      "name": "s_articles.description",
      "label": "Kurzbeschreibung"
    },
    {
      "name": "s_articles.description_long",
      "label": "Beschreibung"
    },
    {
      "name": "s_articles.keywords",
      "label": "Keywords"
    },
    {
      "name": "s_articles_details.additionaltext",
      "label": "Zusätzlicher Text"
    },
    {
      "name": "s_articles_details.weight",
      "label": "Gewicht"
    },
    {
      "name": "s_articles_details.width",
      "label": "Breite"
    },
    {
      "name": "s_articles_details.height",
      "label": "Höhe"
    },
    {
      "name": "s_articles_details.length",
      "label": "Länge"
    },
    {
      "name": "s_articles_details.ean",
      "label": "EAN"
    },
    {
      "name": "s_core_units.unit",
      "label": "Maßeinheit"
    },
    {
      "name": "s_categories",
      "label": "Kategorie"
    },
    {
      "name": "s_article_configurator_groups.id=5",
      "label": "Stocklänge"
    },
    {
      "name": "s_article_configurator_groups.id=6",
      "label": "Größe"
    },
    {
      "name": "s_article_configurator_groups.id=7",
      "label": "Farbvariante"
    },
    {
      "name": "s_article_configurator_groups.id=8",
      "label": "Skigröße"
    },
    {
      "name": "s_article_configurator_groups.id=9",
      "label": "Snowboardgrößen"
    },
    {
      "name": "s_article_configurator_groups.id=10",
      "label": "Inhalt"
    },
    {
      "name": "s_article_configurator_groups.id=11",
      "label": "Auswahl"
    },
    {
      "name": "s_article_configurator_groups.id=12",
      "label": "Geeignet für"
    },
    {
      "name": "s_article_configurator_groups.id=13",
      "label": "Farbe/Material"
    },
    {
      "name": "s_article_configurator_groups.id=14",
      "label": "Farbe"
    },
    {
      "name": "s_article_configurator_groups.id=15",
      "label": "farbe"
    },
    {
      "name": "s_article_configurator_groups.id=16",
      "label": "Hokzfarbe"
    },
    {
      "name": "s_article_configurator_groups.id=17",
      "label": "Eloxidfarbe"
    },
    {
      "name": "s_filter_options.id=1",
      "label": "Artikeltyp"
    },
    {
      "name": "s_filter_options.id=11",
      "label": "Breite"
    },
    {
      "name": "s_filter_options.id=19",
      "label": "Einsatzmöglichkeit"
    },
    {
      "name": "s_filter_options.id=18",
      "label": "Farbe"
    },
    {
      "name": "s_filter_options.id=24",
      "label": "Farbe/Material"
    },
    {
      "name": "s_filter_options.id=10",
      "label": "Features"
    },
    {
      "name": "s_filter_options.id=20",
      "label": "Fisch"
    },
    {
      "name": "s_filter_options.id=8",
      "label": "Fit"
    },
    {
      "name": "s_filter_options.id=16",
      "label": "Geeignet für"
    },
    {
      "name": "s_filter_options.id=14",
      "label": "Geschmack"
    },
    {
      "name": "s_filter_options.id=4",
      "label": "Gewicht"
    },
    {
      "name": "s_filter_options.id=21",
      "label": "Gewürzt"
    },
    {
      "name": "s_filter_options.id=12",
      "label": "Größe"
    },
    {
      "name": "s_filter_options.id=22",
      "label": "Herkunft"
    },
    {
      "name": "s_filter_options.id=15",
      "label": "Inhalt"
    },
    {
      "name": "s_filter_options.id=7",
      "label": "Länge/Größe"
    },
    {
      "name": "s_filter_options.id=3",
      "label": "Material"
    },
    {
      "name": "s_filter_options.id=2",
      "label": "Rohrdurchmesser"
    },
    {
      "name": "s_filter_options.id=17",
      "label": "Volumen"
    },
    {
      "name": "s_filter_options.id=9",
      "label": "Wärmelevel"
    },
    {
      "name": "s_filter_options.id=13",
      "label": "Zielgruppe"
    },
    {
      "name": "s_filter_options.id=23",
      "label": "Zutaten"
    },
    {
      "name": "s_articles_attributes.attr3",
      "label": "Kommentar"
    },
    {
      "name": "s_articles_attributes.attr1",
      "label": "Freitext-1"
    },
    {
      "name": "s_articles_attributes.attr2",
      "label": "Freitext-2"
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

{% tabs %}
{% tab title="Root Level" %}
```javascript
{  
  "limit": number // Aktuell gesetztes Limit - Standard ist soviele Einträge wie vorhanden sind
  "offset": number // Aktuell gesetztes Offset - Standard ist 0
  "total": number // Gesamtanzahl der Produkteigenschaften
  "data": array // Die einzelnen Produkteigenschaften
}
```
{% endtab %}

{% tab title="Data Level" %}
```javascript
{
  "name": string // Identifikator der Eigenschaft
  "label": string // Beschreibung / Bezeichnung der Eigenschaft
}
```
{% endtab %}
{% endtabs %}

### Beispiel

{% tabs %}
{% tab title="API Request - cURL" %}
```bash
curl 'https://shopware.demo.8select.io/cse-api/attributes' \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H '8select-com-fid: 497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H '8select-com-tid: b796a03e-7117-4d12-b40f-e4b06c0ee2dd'
```
{% endtab %}

{% tab title="response.json" %}
```javascript
{
  "limit": 51,
  "offset": 0,
  "total": 51,
  "data": [
    {
      "name": "s_articles.name",
      "label": "Artikel-Bezeichnung"
    },
    {
      "name": "s_articles.metaTitle",
      "label": "Titel"
    },
    {
      "name": "s_articles.description",
      "label": "Kurzbeschreibung"
    },
    {
      "name": "s_articles.description_long",
      "label": "Beschreibung"
    },
    {
      "name": "s_articles.keywords",
      "label": "Keywords"
    },
    {
      "name": "s_articles_details.additionaltext",
      "label": "Zusätzlicher Text"
    },
    {
      "name": "s_articles_details.weight",
      "label": "Gewicht"
    },
    {
      "name": "s_articles_details.width",
      "label": "Breite"
    },
    {
      "name": "s_articles_details.height",
      "label": "Höhe"
    },
    {
      "name": "s_articles_details.length",
      "label": "Länge"
    },
    {
      "name": "s_articles_details.ean",
      "label": "EAN"
    },
    {
      "name": "s_core_units.unit",
      "label": "Maßeinheit"
    },
    {
      "name": "s_categories",
      "label": "Kategorie"
    },
    {
      "name": "s_article_configurator_groups.id=5",
      "label": "Stocklänge"
    },
    {
      "name": "s_article_configurator_groups.id=6",
      "label": "Größe"
    },
    {
      "name": "s_article_configurator_groups.id=7",
      "label": "Farbvariante"
    },
    {
      "name": "s_article_configurator_groups.id=8",
      "label": "Skigröße"
    },
    {
      "name": "s_article_configurator_groups.id=9",
      "label": "Snowboardgrößen"
    },
    {
      "name": "s_article_configurator_groups.id=10",
      "label": "Inhalt"
    },
    {
      "name": "s_article_configurator_groups.id=11",
      "label": "Auswahl"
    },
    {
      "name": "s_article_configurator_groups.id=12",
      "label": "Geeignet für"
    },
    {
      "name": "s_article_configurator_groups.id=13",
      "label": "Farbe/Material"
    },
    {
      "name": "s_article_configurator_groups.id=14",
      "label": "Farbe"
    },
    {
      "name": "s_article_configurator_groups.id=15",
      "label": "farbe"
    },
    {
      "name": "s_article_configurator_groups.id=16",
      "label": "Hokzfarbe"
    },
    {
      "name": "s_article_configurator_groups.id=17",
      "label": "Eloxidfarbe"
    },
    {
      "name": "s_filter_options.id=1",
      "label": "Artikeltyp"
    },
    {
      "name": "s_filter_options.id=11",
      "label": "Breite"
    },
    {
      "name": "s_filter_options.id=19",
      "label": "Einsatzmöglichkeit"
    },
    {
      "name": "s_filter_options.id=18",
      "label": "Farbe"
    },
    {
      "name": "s_filter_options.id=24",
      "label": "Farbe/Material"
    },
    {
      "name": "s_filter_options.id=10",
      "label": "Features"
    },
    {
      "name": "s_filter_options.id=20",
      "label": "Fisch"
    },
    {
      "name": "s_filter_options.id=8",
      "label": "Fit"
    },
    {
      "name": "s_filter_options.id=16",
      "label": "Geeignet für"
    },
    {
      "name": "s_filter_options.id=14",
      "label": "Geschmack"
    },
    {
      "name": "s_filter_options.id=4",
      "label": "Gewicht"
    },
    {
      "name": "s_filter_options.id=21",
      "label": "Gewürzt"
    },
    {
      "name": "s_filter_options.id=12",
      "label": "Größe"
    },
    {
      "name": "s_filter_options.id=22",
      "label": "Herkunft"
    },
    {
      "name": "s_filter_options.id=15",
      "label": "Inhalt"
    },
    {
      "name": "s_filter_options.id=7",
      "label": "Länge/Größe"
    },
    {
      "name": "s_filter_options.id=3",
      "label": "Material"
    },
    {
      "name": "s_filter_options.id=2",
      "label": "Rohrdurchmesser"
    },
    {
      "name": "s_filter_options.id=17",
      "label": "Volumen"
    },
    {
      "name": "s_filter_options.id=9",
      "label": "Wärmelevel"
    },
    {
      "name": "s_filter_options.id=13",
      "label": "Zielgruppe"
    },
    {
      "name": "s_filter_options.id=23",
      "label": "Zutaten"
    },
    {
      "name": "s_articles_attributes.attr3",
      "label": "Kommentar"
    },
    {
      "name": "s_articles_attributes.attr1",
      "label": "Freitext-1"
    },
    {
      "name": "s_articles_attributes.attr2",
      "label": "Freitext-2"
    }
  ]
}
```
{% endtab %}
{% endtabs %}



