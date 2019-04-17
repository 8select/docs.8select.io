# Integration

### API ID und Feed ID

{% hint style="info" %}
In manchen Code-Snippets befinden sich Platzhalter die mit richtigen Werten ersetzt werden müssen. Die Werte finden Sie in der MCON unter Settings -&gt; Plugin.

**`<API-ID>`** bzw. **`apiId`**  muss durch die API ID ersetzt werden, die 8select zur Verfügung stellt.   
Zum Beispiel `68aeb083-e34b-45bc-9551-583cf33d774c`

**`<FEED-ID>`** bzw. **`feedId`**  muss durch die Feed ID ersetzt werden, die 8select zur Verfügung stellt.   
Zum Beispiel `cfd32492-fef9-421f-a399-d9d8e933db62`
{% endhint %}

## Wie wird die 8select.CSE integriert?

Die 8select-CSE wird mit Hilfe des JavaScript SDK eingebunden und muss nicht heruntergeladen werden. Es wird einfach über ein JavaScript-Codeausschnitt auf der Webseite im HTML platziert.

Die optimale Platzierung ist die Platzierung als erstes `<script>` Element auf der Seite, noch über dem `<body>` Element.

Das SDK wird asynchron geladen ohne Ladevorgänge von anderen Elementen auf der Webseite zu blockieren.

### SDK laden

{% page-ref page="sdk-snippet.md" %}

