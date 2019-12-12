# Abfrage von Produkteigenschaften für Variantenbildung

{% api-method method="get" host="https://shopware.demo.8select.io" path="/cse-api/variant-dimensions" %}
{% api-method-summary %}
Produkteigenschaften die Varianten bilden
{% endapi-method-summary %}

{% api-method-description %}
Über den Endpunkt können alle Produkteigenschaften abgefragt werden die der Shop für die Bildung von Varianten nutzt.  
Es werden lediglich die Identifikatoren und Bezeichnungen der Eigenschaften zurückgegeben.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```javascript
{
  "limit": 13,
  "offset": 0,
  "total": 13,
  "data": [
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
Wenn im Request die Header für die Authentifizierung fehlen.
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
curl 'https://shopware.demo.8select.io/cse-api/variant-dimensions' \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H '8select-com-fid: 497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H '8select-com-tid: b796a03e-7117-4d12-b40f-e4b06c0ee2dd'
```
{% endtab %}

{% tab title="response.json" %}
```javascript
{
  "limit": 13,
  "offset": 0,
  "total": 13,
  "data": [
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
    }
  ]
}
```
{% endtab %}
{% endtabs %}



