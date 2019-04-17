# Einleitung

Damit die 8select.CSE in einem Shop nutzbar ist, muss sich der Shop mit der CSE verbinden.  
Dabei wird zum Beispiel die Shop URL übertragen aber auch die Informationen darüber wie und wo die 8select.CSE die Produktdaten des Shops abfragen kann.

![](../.gitbook/assets/schema.jpg)

### Authentifizierung

Der Endpunkt prüft die Legitimität der Anfrage in dem die im  Request Header gesendeten Werte für **`<API-ID>`** und **`<FEED-ID>`** abgeglichen werden.

