# REST API - Pull Prinzip

Die 8select.CSE ruft die Produktdaten von einer vom Shop bereitgestellten REST API ab.  
Der Datenaustausch findet im JSON Format statt. Die Authentifizierung erfolgt über Key und Secret Key im Header.

* HTTP REST API
* API muss Seitenweise abrufbar sein \(pagination\)
* API Inhalte werden im Format `application/json` übertragen
* Authentifizierung erfolgt via API ID und Feed ID im Header

{% hint style="info" %}
Der Header **`Content-Type`** muss bei Anfrage und Antworten im JSON Format auf **`application/json`** gesetzt sein.
{% endhint %}

### Authentifizierung

Der Endpunkt prüft die Legitimität der Anfrage in dem die im Shop hinterlegten Werte für **`<API-ID>`** und **`<FEED-ID>`** mit den Werten im Request Header abgeglichen werden.

