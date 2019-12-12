# API

{% api-method method="put" host="https://sc.8select.io/shops" path="/:apiId/:feedId" %}
{% api-method-summary %}
Shop bei der 8select.CSE registrieren
{% endapi-method-summary %}

{% api-method-description %}
Stellt eine Verbindung zwischen Shop und 8select.CSE her.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="apiId" type="string" required=true %}
API ID aus MCON
{% endapi-method-parameter %}

{% api-method-parameter name="feedId" type="string" required=true %}
Feed ID aus MCON
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Content-Type" type="string" required=false %}
application/json
{% endapi-method-parameter %}

{% api-method-parameter name="8select-com-fid" type="string" required=true %}
Feed ID aus MCON
{% endapi-method-parameter %}

{% api-method-parameter name="8select-com-tid" type="string" required=true %}
API ID aus MCON
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="api" type="object" required=true %}
API Endpunkte für Produktdaten
{% endapi-method-parameter %}

{% api-method-parameter name="api.attributes" type="string" required=true %}
URL zum Abrufen aller Produktattribute \(ohne Werte\)
{% endapi-method-parameter %}

{% api-method-parameter name="api.products" type="string" required=true %}
URL zum Abrufen der Produktdaten
{% endapi-method-parameter %}

{% api-method-parameter name="api.variantDimensions" type="string" required=true %}
URL zum Abrufen aller Produktattribute die zur Variantenbildung genutzt werden
{% endapi-method-parameter %}

{% api-method-parameter name="plugin" type="object" required=true %}
Informationen zum Plugin
{% endapi-method-parameter %}

{% api-method-parameter name="plugin.version" type="string" required=true %}
Version des Plugins
{% endapi-method-parameter %}

{% api-method-parameter name="shop" type="object" required=true %}
Informationen zum Shop
{% endapi-method-parameter %}

{% api-method-parameter name="shop.software" type="string" required=true %}
Eingesetzte Shopsoftware
{% endapi-method-parameter %}

{% api-method-parameter name="shop.url" type="string" required=true %}
URL des Shops
{% endapi-method-parameter %}

{% api-method-parameter name="shop.version" type="string" required=true %}
Version der eingesetzten Shopsoftware
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Verbindung hergestellt
{% endapi-method-response-example-description %}

```
{       
  "api": {
    "attributes": "https://shopware.demo.8select.io/cse-api/attributes",
    "products": "https://shopware.demo.8select.io/cse-api/products",
    "variantDimensions": "https://shopware.demo.8select.io/cse-api/variant-dimensions"
  },
  "plugin": {
    "version": "3.0.0"
  },
  "shop": {    
    "software": "Shopware",
    "url": "https://shopware.demo.8select.io",
    "version": "5.5.3"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### **Beispiel**

{% tabs %}
{% tab title="API Request - cURL" %}
```bash
curl -X PUT 'https://sc.8select.io/shops/b796a03e-7117-4d12-b40f-e4b06c0ee2dd/497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H 'Content-Type: application/json; charset=utf-8' \
  -H '8select-com-fid: 497d4510-29c4-4160-adac-42ebb32a09c0' \
  -H '8select-com-tid: b796a03e-7117-4d12-b40f-e4b06c0ee2dd' \
  -d '{"api":{"attributes":"https://shopware.demo.8select.io/cse-api/attributes","products":"https://shopware.demo.8select.io/cse-api/products","variantDimensions":"https://shopware.demo.8select.io/cse-api/variant-dimensions"},"plugin":{"version":"3.0.0"},"shop":{"software":"Shopware","url":"https://shopware.demo.8select.io","version":"5.5.3"}}'
```
{% endtab %}

{% tab title="response.json" %}
```javascript
{       
  "api": {
    "attributes": "https://shopware.demo.8select.io/cse-api/attributes",
    "products": "https://shopware.demo.8select.io/cse-api/products",
    "variantDimensions": "https://shopware.demo.8select.io/cse-api/variant-dimensions"
  },
  "plugin": {
    "version": "3.0.0"
  },
  "shop": {    
    "software": "Shopware",
    "url": "https://shopware.demo.8select.io",
    "version": "5.5.3"
  }
}ja
```
{% endtab %}
{% endtabs %}

