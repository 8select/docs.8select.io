# API

### Übersicht

* REST
* Datenaustausch im JSON Format - `content-type: application/json` 
* Authentifizierung via Key und Secret Keys im Header

### Authentifizierung

Der Endpunkt prüft die Legitimität der Anfrage in dem die im Shop Plugin gesetzte TID und FID mit Werten im Request Header abgeglichen werden.

* der Header `8select-com-tid` muss der im Shop hinterlegten von 8select gestellten API-ID entsprechen
* der Header `8select-com-fid` muss der im Shop hinterlegten von 8select gestellten FEED-ID entsprechen
* sind die Header nicht im Request enthalten, so antwortet die API mit einem HTTP 404
* sind die Daten im Shop nicht hinterlegt, so antwortet die API mit einem HTTP 500
* sind die Daten im Shop hinterlegt, stimmen jedoch nicht mit denen im Request überein, so antwortet die API mit einem HTTP 403

