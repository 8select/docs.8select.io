# Pflichtfelder

## Sku

Die Artikelnummer \(SKU\) ist einzigartig, sie enthält Modell, Farbe und Größe. Die SKU ist der Hauptidentifikator für einen konkreten Artikel \(Variante\) in einem Shop.

Die SKU wird verwendet um einen Artikel aus dem Shop in der 8select CSE zu finden.

### Beispiele

```text
827748001
```

## Mastersku

Die Master-SKU ist einzigartig, sie enthält Modell und Farbe. Die Master-SKU ist der Hauptidentifikator für einen Artikel \(Elternartikel\) in einem Shop.

Die Master-SKU wird verwendet um eine Beziehung zwischen Elternartikel und Varianten herzustellen.

### Beispiele

```text
8277480
```

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

## Model

Ein Modell bezeichnet das Grundprodukt. Ein Modell kann in mehreren Ausführungen vorkommen, die sich z.B. in Größe, Farbe oder Muster unterschieden.

Beispiel: Das Modell `Arie` \(8277\) gibt es in den 3 Farben: `blau` \(480\), `rot` \(481\), `gelb` \(482\) und in den 4 Größen: `S` \(01\), `M` \(02\), `L` \(03\), `XL` \(04\), also 12 Ausführungen. Jede Ausführung hat eine eindeutige Artikelnummer.

### Beispiele

| model | mastersku | sku |
| :--- | :--- | :--- |
| 8277 | 8277-480 | 8277-480-01 |

## Name

Standardbezeichnung für den Artikel so wie er normalerweise in der Artikeldetailansicht genutzt wird.

### Beispiele

```text
Desigual Sweatjacke
```

## Kategorie

Bezeichnung der Artikelgruppen, die meist so in der Shopnavigation verwendet werden.

### Beispiele

```text
Sweatshirts & -jacken
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

## Marke

Markenname bzw. Hersteller eines Artikels.

### Beispiele

```text
Desigual
HUGO BOSS
Betty Barclay
```

## Farbe

Die exakte Farbbezeichnung des Artikels.

### Beispiele

```text
rot
grün
gelb
schwarz-rot-gold
Burnished Rosè
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

## Beschreibung

Der Beschreibungstext zum Artikel im HTML-Format.

### Beispiele

```markup
<p>
Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven 
Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch 
gestaltet.<br><br>    
- modisch nach innen gezogenen Seitennähte<br>  
- zwei Nahttaschen auf Hüfthöhe<br>  
- Rückenteil modisch verlängert<br>  
- Rückenlänge bei Gr. S (36): ca. 64 cm<br>  
- unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm<br><br>   
Material: 51% Baumwolle, 45% Polyester, 4% Elasthan<br><br>    
---Pflegehinweise---<br>  
- Maschinenwäsche bei 30°, von links<br>  
- nicht für den Trockner geeignet<br>
</p>
```

