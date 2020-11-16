# 8.SET Mail \(Beta\)

Mit Hilfe von 8.SET Mail kann ein Produkt-Set passend zu einer Liste von Artikeln in eine E-Mail eingebunden werden. Unsere APIs liefern ein Bild von dem Produkt-Set sowie einen Link über den der Kunde auf die Artikeldetailseite mit dem soeben gezeigten Produkt-Set kommt.

Das Produkt-Set Bild ist in 3 verschiedenen Auflösungen abrufbar, so dass mit Hilfe von CSS je nach Gerät eine passende Größe angezeigt wird.

{% hint style="info" %}
Aktuell ist der Touchpoint noch in der Beta-Phase. Das heißt wir können mit Hilfe von Feedback auch noch sehr schnell Anpassungen vornehmen.
{% endhint %}

{% api-method method="get" host="https://mail.8select.io" path="/:apiId/:size/sys?skus=:list-of-skus&id=:unique-mail-id" %}
{% api-method-summary %}
Produkt-Set als Bild abrufen
{% endapi-method-summary %}

{% api-method-description %}
Gibt ein Produkt-Set als Bild in der angefragten Größe zurück.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="apiId" type="string" required=true %}
API ID aus MCON
{% endapi-method-parameter %}

{% api-method-parameter name="size" type="string" required=true %}
small \| medium \| large - Größe des Bildes
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-query-parameters %}
{% api-method-parameter name="skus" type="string" required=true %}
1-n Komma separierte SKUs  
z.Bsp. aus einer Bestellung
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
Unique ID - über diese kann der entsprechende Link zum Produkt-Set abgerufen werden.
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Wenn ein Produkt-Set gefunden wird.
{% endapi-method-response-example-description %}

```
Produkt-Set als Bild.
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=204 %}
{% api-method-response-example-description %}
Wenn kein Produkt-Set gefunden wird.
{% endapi-method-response-example-description %}

```
1x1 weißes Bild.
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

![Beispiel Antwort](../../.gitbook/assets/bildschirmfoto-2020-04-23-um-15.26.41.png)

{% api-method method="get" host="https://landing.8select.io" path="/:apiId/mail/:id" %}
{% api-method-summary %}
Weiterleitung zum Produkt-Set abrufen
{% endapi-method-summary %}

{% api-method-description %}
Gibt eine Weiterleitung für die angefragte `id` zurück.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="apiId" type="string" required=true %}
API ID aus MCON
{% endapi-method-parameter %}

{% api-method-parameter name="id" type="string" required=true %}
Unique ID - diese muss auch für das abrufen des Produkt-Set Bildes benutzt werden.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=301 %}
{% api-method-response-example-description %}
Weiterleitung zum Produkt-Set.
{% endapi-method-response-example-description %}

```http
location: https://www.all4golf.de/golfbekleidung-herren/polos/cross-poloshirt-neo-kurzarm-navy-6750293?number=6750293&scrollToSet=1
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% hint style="info" %}
Parameter zum Beispiel für das User Tracking hinterlegen wir aktuell individuell in unserem Backend. Bitte sprechen Sie mit uns.
{% endhint %}

