# Verbindung vom Shop zu 8select herstellen

{% api-method method="put" host="https://sc.8select.io/shops" path="/:apiId/:feedId" %}
{% api-method-summary %}
Shop registrieren
{% endapi-method-summary %}

{% api-method-description %}
Stellt eine Verbindung zwischen Shop und 8select.CSE her.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
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

{% api-method-parameter name="plugin" type="object" required=false %}
Informationen zum Plugin
{% endapi-method-parameter %}

{% api-method-parameter name="shop" type="object" required=true %}
Informationen zum Shop
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
    "url": "https://shopware.demo.8select.io",
    "software": "Shopware",
    "version": "5.5.3"
  }
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

#### **Beispiel Body**

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
    "url": "https://shopware.demo.8select.io",
    "software": "Shopware",
    "version": "5.5.3"
  }
}
```

