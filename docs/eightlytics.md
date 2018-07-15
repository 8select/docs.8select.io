# README

[Übersicht](https://docs.8select.io/CSE-integration-manual/)

* [CSE Performance-Tracking aka. Eightlytics für KPIs und Abrechnung](eightlytics.md#cse-performance-tracking-aka-eightlytics-für-kpis-und-abrechnung)
  * [Eightlytics einbinden](eightlytics.md#eightlytics-einbinden)
  * [Tracking von Transaktionen](eightlytics.md#tracking-von-transaktionen)
  * [API](eightlytics.md#api)
    * [eightlytics\('purchase', order\)](eightlytics.md#eightlyticspurchase-order)

## CSE Performance-Tracking aka. Eightlytics für KPIs und Abrechnung

Eightlytics ist das Web Analytics Tool von 8select, ähnlich wie z.B. Google Analytics oder Webtrekk. Mit Hilfe unseres Web Analytics Tools sammeln wir Daten zur Nutzung der Widgets. Im Performance Dashboard können Sie so jederzeit die Performance der CSE einsehen.

### Eightlytics einbinden

Eightlytics wird automatisch durch das einbinden des 8select-CSE JavaScript SDKs geladen, sofern es benötigt wird.

Siehe dazu [Setup](setup.md)

### Tracking von Transaktionen

Für die Auswertung der Umsätze die über die 8select-CSE kommen, müssen Sie einen zweiten JavaScript Codeausschnitt einbinden. Dies muss auf der Seite die nach einem erfolgreichen Checkout angezeigt wird erfolgen.

Der Codeausschnitt muss im HTML an beliebiger Stelle nach dem Codeausschnitt für das Laden des 8select-CSE JavaScript-SDKs eingefügt werden.

**ACHTUNG** - Preise müssen in Cent übertragen werden - also aus `199,95 €` wird `19995`.

```javascript
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

### API

#### eightlytics\('purchase', order\)

**order**

| field | type | required | description |
| --- | --- | --- | --- |
| customerid | string | required | unique customer identifier |
| orderid | string | required | unique transaction identifier |
| products | array of product | required | which products does the order contain |

**product**

| field | type | required | description |
| --- | --- | --- | --- |
| sku | string | required | product identifier |
| amount | integer | required | how many units are added to the cart |
| price | integer | required | what does one unit cost in _**euro cent**_ |

```javascript
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
```

