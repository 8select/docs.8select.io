# Tracking Snippet

Für die Auswertung der Umsätze die über die 8select-CSE kommen, müssen Sie das [**SDK**](../integration/#wie-wird-die-8select-cse-integriert) **einbinden** und **zusätzlich einen zweiten** JavaScript Codeausschnitt. Dies muss auf der Seite die nach einem erfolgreichen Checkout angezeigt wird erfolgen.

Der Codeausschnitt muss im HTML an beliebiger Stelle nach dem Codeausschnitt für das Laden des 8select.CSE JavaScript-SDKs eingefügt werden.

{% hint style="info" %}
**ACHTUNG** - Preise müssen in Cent übertragen werden.  
Für ein Artikel für `199,95 €` muss der Wert `19995`übertragen werden.
{% endhint %}

```javascript
<script type="text/javascript">
    //code für das 8select-CSE JavaScript-SDK - siehe anderes Snippet
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

### Integration via Tag Manager - zum Beispiel GTM

Eine Integration via \(Google\) Tag Manager ist mit dem obigen Snippet problemlos möglich. Die entsprechenden Werte werden dann einfach aus dem GTM Data Layer befüllt. Auch hier bitte beachten, dass die Preise in Cent übertragen werden müssen.

