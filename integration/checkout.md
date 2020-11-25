# Checkout

Die Vergütung erfolgt performancebasiert, dass heißt nur für Produkte die über unsere Widgets gekauft wurden fällt eine Provision an. Um diese Produkte zu ermitteln werden die Käufe im Shop mit den Interaktionen in unseren Widgets abgeglichen. Dazu müssen alle Shopumsätze übermitteln werden. Die Übermittlung erfolgt ohne personenbezogene Daten und enthält lediglich die einzelnen Auftragspositionen.

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
        customerid: '1234',
        orderid: '1234',
        products: [
          {
            sku: '12345',
            amount: 3,
            price: 1199
          },
          {
            sku: '456',
            amount: 1,
            price: 19995
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

