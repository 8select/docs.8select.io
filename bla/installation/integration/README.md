# Integration

### API-ID

{% hint style="info" %}
In manchen Code-Snippets befindet sich der Wert**`<API-ID>`**.  
Dieser muss durch die API-ID ersetzt werden, die 8select zur Verfügung stellt.   
Zum Beispiel `68aeb083-e34b-45bc-9551-583cf33d774c`

Die API ID finden Sie in der MCON.
{% endhint %}

## Wie wird die 8select.CSE integriert?

Die 8select-CSE wird mit Hilfe des JavaScript SDK eingebunden und muss nicht heruntergeladen werden. Es wird einfach über ein JavaScript-Codeausschnitt auf der Webseite im HTML platziert.

Die optimale Platzierung ist die Platzierung als erstes `<script>` Element auf der Seite, noch über dem `<body>` Element.

Das SDK wird asynchron geladen ohne Ladevorgänge von anderen Elementen auf der Webseite zu blockieren.

### SDK laden

{% page-ref page="sdk-snippet.md" %}

