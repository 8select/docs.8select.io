# Authentifizierung

Der Endpunkt prüft die Legitimität der Anfrage in dem die im Shop hinterlegten Werte für **`<API-ID>`** und **`<FEED-ID>`** mit den Werten im Request Header abgeglichen werden.

* der Header `8select-com-tid` muss der im Shop hinterlegten von 8select gestellten API ID entsprechen
* der Header `8select-com-fid` muss der im Shop hinterlegten von 8select gestellten Feed ID entsprechen
* sind die Header nicht im Request enthalten, so muss die API mit einem HTTP 404 antworten
* sind die Daten im Shop nicht hinterlegt, so muss die API mit einem HTTP 500 antworten
* sind die Daten im Shop hinterlegt, stimmen jedoch nicht mit denen im Request überein, so muss die API mit einem HTTP 403 antworten

