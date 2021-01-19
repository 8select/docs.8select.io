# Details

## SKU

Die Artikelnummer \(SKU\) ist einzigartig. Die SKU ist der Hauptidentifikator für einen konkreten Artikel \(Variante\) in einem Shop.

### Beispiele

```text
8277-480-01
8febdd77-c6a6-40f6-b322-9620680c7bc2
42
A-2-21
```

{% hint style="info" %}
Die SKU wird verwendet um Content zu einem Artikel zu finden, um einen Artikel in den Warenkorb zu legen und für den Abgleich der Käufe mit den Interaktionen in unseren Widgets.
{% endhint %}

## Bestellstatus

Der Status gibt Auskunft über die Bestellbarkeit einer Variante.

### Beispiele

bestellbar

```text
1
```

nicht bestellbar

```text
0
```

## Name

Standardbezeichnung für den Artikel so wie er normalerweise in der Artikeldetailansicht genutzt wird.

### Beispiele

```text
Desigual Sweatjacke
```

## Streichpreis

Der originale Preis bzw. UVP. Im Shop meist als durchgestrichener Preis dargestellt.

Ohne Währungsangaben und in Cent.

### Beispiele

```text
8000
19939
```

## Angebotspreis

Der Preis zu dem der Artikel verkauft wird.

Ohne Währungsangaben und in Cent.

### Beispiele

```text
6995
13750
```

## Produkt URL

Deeplink der direkt zur Detailseite im Shop der Variante führt.

### Beispiele

```text
https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387
https://www.bettybarclay.com/de/vera-mont-cocktail-kleid-21254528.html?farbe=burnished-ros&groesse=38
```

## Bilder

Alle verfügbaren Artikelbilder der Variante in der höchsten Auflösung.  
Mehrere Bilder werden mit Pipe `|` getrennt.  
An Position 1 ist idealerweise ein Hollowman-Bild bzw. Produktbild ohne Model.

### Beispiele

```javascript
https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$

https://cdn.8select.io/image1.jpg|https://cdn.8select.io/image2.jpg
```

