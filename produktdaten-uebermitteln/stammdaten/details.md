# Details und Beispiele

## SKU

Die Artikelnummer \(SKU\) ist einzigartig. Die SKU ist der Hauptidentifikator für einen konkreten Artikel \(Variante\) in einem Shop.

### Beispiele

```text
8277-480-01
8febdd77-c6a6-40f6-b322-9620680c7bc2
42
A-2-21
```

{% hint style="warning" %}
Die SKU wird verwendet um Content zu einem Artikel zu finden, um einen Artikel in den Warenkorb zu legen und für den Abgleich der Käufe mit den Interaktionen in unseren Widgets.   
Das heißt dieser Wert muss auch im Shop für die Widgets und im Checkout verfügbar sein.
{% endhint %}

## Master-SKU

Die Master-SKU ist einzigartig, sie enthält Modell und Farbe. Die Master-SKU ist der Hauptidentifikator für einen Artikel \(Elternartikel\) in einem Shop.

Die Master-SKU wird verwendet um eine Beziehung zwischen Elternartikel und Varianten herzustellen.  
  
Elternartikel: Hose - Farbe blau  
Variante: Hose - Farbe blau - Größe M

### Beispiele

```text
8277-480
Hose-Blau
```

## Modell

Ein Modell bezeichnet das Grundprodukt. Ein Modell kann in mehreren Ausführungen vorkommen, die sich z.B. in Größe, Farbe oder Muster unterschieden.

Das Modell `Arie` \(8277\) gibt es in den 3 Farben: `blau` \(480\), `rot` \(481\), `gelb` \(482\) und in den 4 Größen: `S` \(01\), `M` \(02\), `L` \(03\), `XL` \(04\), also 12 Ausführungen. Jede Ausführung hat eine eindeutige Artikelnummer.  
  
Model: Hose Arie  
Elternartikel: Hose Arie - Farbe blau  
Variante: Hose Arie - Farbe blau - Größe M

### Beispiele

| model | mastersku | sku |
| :--- | :--- | :--- |
| 8277 | 8277-480 | 8277-480-01 |
| Hose-Arie | Hose-Arie-Blau | Hose-Arie-Blau-M |

## Bestellstatus

Der Status gibt Auskunft über die Bestellbarkeit einer Variante. Es kann ein Flag sein \(0/1\) oder aber die Menge der verfügbaren Artikel.

### Beispiele

bestellbar

```text
1
3
12
```

nicht bestellbar

```text
0
```

## Größe

Größenbezeichnung des Artikels.

### Beispiele

```text
38
L
32/32
32 L
M-L
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

