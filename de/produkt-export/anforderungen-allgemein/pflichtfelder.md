# Pflichtfelder

## Sku

Die Artikelnummer \(SKU\) ist einzigartig, sie enthält Modell, Farbe und Größe. Die SKU ist der Hauptidentifikator für einen konkreten Artikel \(Variante\) in einem Shop.

Die SKU wird verwendet um einen Artikel aus dem Shop in der 8select CSE zu finden.

### Beispiele

```text
827748001
```

Die Master-SKU ist einzigartig, sie enthält Modell und Farbe. Die Master-SKU ist der Hauptidentifikator für einen Artikel \(Elternartikel\) in einem Shop.

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

Alle verfügbaren Artikelbilder der Variante in der höchsten Auflösung. Mehrere Bilder werden als array übertragen.

### Beispiele

```text
[
  "https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$"
]

[  
  "https://cdn1.bettybarclay.com/out/pictures/1/Cocktail-Kleid_2_182_21254528_6389.v6.jpg",
  "https://cdn1.bettybarclay.com/out/pictures/3/Cocktail-Kleid_2_182_21254528_6389.v6.jpg",
  "https://cdn1.bettybarclay.com/out/pictures/6/Cocktail-Kleid_2_182_21254528_6389.v6.jpg"
  ]
```


