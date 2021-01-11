# Checkout

Die Vergütung erfolgt performancebasiert, dass heißt nur für Produkte die über unsere Widgets gekauft wurden fällt eine Provision an. Um diese Produkte zu ermitteln werden die Käufe im Shop mit den Interaktionen in unseren Widgets abgeglichen. Dazu müssen alle Shopumsätze übermitteln werden. Die Übermittlung erfolgt ohne personenbezogene Daten und enthält lediglich die einzelnen Auftragspositionen.

{% hint style="warning" %}
Für **`price`** muss der Preis in Cent als **`integer`** übertragen werden.  
Für einen Artikel der 199,95 € kostet, muss der Wert `19995` übertragen werden.

Für **`sku`** muss der gleiche Wert wie im [Produkt Export](../produktdaten-uebermitteln/stammdaten/details.md#sku) genutzt werden. Der Wert muss als **`string`** übertragen werden.
{% endhint %}

```javascript
<script type="text/javascript">
  //////
  // 8SELECT JavaScript-SDK
  //////
</script>

<script type="text/javascript">
  window.eightlytics(
    'purchase',
      {
        customerid: '1234', // string
        orderid: '1234', // string
        products: [
          {
            sku: '12345', // string
            amount: 3, // integer
            price: 1199 // integer - price in cent
          },
          {
            sku: '456', // string
            amount: 1, // integer
            price: 19995 // integer
          }
        ]
    }  
  );
</script>
```

{% hint style="info" %}
Die **customerid** wird genutzt um die Ausspielung von Content zu optimieren. Wird die customerid anonymisiert, sollte dies deterministisch erfolgen.
{% endhint %}

{% hint style="info" %}
Die **orderid** kann genutzt werden um auf Anfrage einen Abgleich unserer Analytics Daten mit den Analytics Daten des Shops zu machen. Zum Beispiel für Stichproben. Wenn dies gewünscht wird, darf die orderid nicht anonymisiert übermittelt werden.
{% endhint %}

