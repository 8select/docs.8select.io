# Pflichtfelder Beispiele

## sku - prop_sku

Die Artikelnummer (SKU) ist einzigartig, sie enthält Modell, Farbe und Größe. Die SKU ist der Hauptidentifikator für einen konkreten Artikel (Variante) in einem Shop.

Die SKU wird verwendet um einen Artikel aus dem Shop in der 8select CSE zu finden.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| sku | prop_sku | `string` |


### Beispiele

```
827748001
```

## mastersku - prop_parentSku

Die Master-SKU ist einzigartig, sie enthält Modell und Farbe. Die Master-SKU ist der Hauptidentifikator für einen Artikel (Elternartikel) in einem Shop.

Die Master-SKU wird verwendet um eine Beziehung zwischen Elternartikel und Varianten herzustellen.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| mastersku | prop_parentSku | `string` |

### Beispiele

```
8277480
```

## status - prop_isInStock

Der Status gibt Auskunft über die Bestellbarkeit einer Variante.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| status | prop_isInStock | `integer` |

### Beispiele

bestellbar
```
1
```

nicht bestellbar
```
0
```

## model - prop_model

Ein Modell bezeichnet das Grundprodukt. Ein Modell kann in mehreren Ausführungen vorkommen, die sich z.B. in Größe, Farbe oder Muster unterschieden.

Beispiel: Das Modell `Arie` (8277) gibt es in den 3 Farben: `blau` (480), `rot` (481), `gelb` (482) und in den 4 Größen: `S` (01), `M` (02), `L` (03), `XL` (04), also 12 Ausführungen. Jede Ausführung hat eine eindeutige Artikelnummer.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| model | prop_model | `string` |

### Beispiele

| model | mastersku | sku |
| --- | --- | --- |
| 8277 | 8277-480 | 8277-480-01 |


## name1 - prop_name

Standardbezeichnung für den Artikel so wie er normalerweise in der Artikeldetailansicht genutzt wird.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| name1 | prop_name | `string` |

### Beispiele

```
Desigual Sweatjacke
```

## kategorie1

Bezeichnung der Artikelgruppen, die meist so in der Shopnavigation verwendet werden.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| kategorie1 | - | `string` |

### Beispiele

```
Sweatshirts & -jacken
```

## streich_preis - prop_retailPrice

Der orignale Preis bzw. UVP. Im Shop meist als durchgestrichener Preis dargestellt.

Ohne Währungsangaben und mit Punkt als Dezimaltrenner formatiert.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| streich_preis | prop_retailPrice | `string` oder Art von `float` mit 2 Dezimalstellen |

### Beispiele

```
80.00
199.39
```

## angebots_preis - prop_discountPrice

Der Preis zu dem der Artikel verkauft wird.

Ohne Währungsangaben und mit Punkt als Dezimaltrenner formatiert.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| angebots_preis | prop_discountPrice | `string` oder Art von `float` mit 2 Dezimalstellen |

### Beispiele

```
69.95
137.50
```

## groesse - prop_size

Größenbezeichnung des Artikels.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| groesse | prop_size | `string` |

### Beispiele

```
38
L
32/32
32 L
M-L
```

## marke - prop_brand

Markenname bzw. Hersteller eines Artikels.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| marke | prop_brand | `string` |

### Beispiele

```
Desigual
HUGO BOSS
Betty Barclay
```

## farbe - prop_color

Die exakte Farbbezeichnung des Artikels.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| farbe | prop_color | `string` |

### Beispiele

```
rot
grün
gelb
schwarz-rot-gold
Burnished Rosè
```

##  produkt_url | prop_url

Deeplink der direkt zur Detailseite im Shop der Variante führt.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| produkt_url | prop_url | `string` |

### Beispiele

```
https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387
https://www.bettybarclay.com/de/vera-mont-cocktail-kleid-21254528.html?farbe=burnished-ros&groesse=38
```

## bilder - images

Alle verfügbaren Artikelbilder der Variante in der höchsten Auflösung. Mehrere Bilder werden mit einem Pipe `|` getrennt.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| bilder | images | `string` |

### Beispiele

```
https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$
https://cdn1.bettybarclay.com/out/pictures/1/Cocktail-Kleid_2_182_21254528_6389.v6.jpg|https://cdn1.bettybarclay.com/out/pictures/3/Cocktail-Kleid_2_182_21254528_6389.v6.jpg|https://cdn1.bettybarclay.com/out/pictures/6/Cocktail-Kleid_2_182_21254528_6389.v6.jpg
```

## beschreibung - prop_description

Der Beschreibungstext zum Artikel im HTML-Format.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| beschreibung | prop_description | HTML `string` |

### Beispiele

```
<p>Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.<br><br>    - modisch nach innen gezogenen Seitennähte<br>  - zwei Nahttaschen auf Hüfthöhe<br>  - Rückenteil modisch verlängert<br>  - Rückenlänge bei Gr. S (36): ca. 64 cm<br>  - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm<br><br>    Material: 51% Baumwolle, 45% Polyester, 4% Elasthan<br><br>    ---Pflegehinweise---<br>  - Maschinenwäsche bei 30°, von links<br>  - nicht für den Trockner geeignet<br>
``` 

## beschreibung1

Der Beschreibungstext zum Artikel in Text-Format.

| Spalte product\_feed | Spalte property\_feed | Datentyp |
| --- | --- | --- |
| beschreibung1 | - | `string` |

### Beispiele

```
Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.- modisch nach innen gezogenen Seitennähte - zwei Nahttaschen auf Hüfthöhe  - Rückenteil modisch verlängert - Rückenlänge bei Gr. S (36): ca. 64 cm - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm Material: 51% Baumwolle, 45% Polyester, 4% Elasthan ---Pflegehinweise--- - Maschinenwäsche bei 30°, von links - nicht für den Trockner geeignet
```
