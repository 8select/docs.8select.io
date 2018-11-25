# Examples

## sku - prop\_sku

The item number \(SKU\) is unique, it contains information about model, color and size. The SKU is the main identifier of a certain item \(variant\) in a shop.

The SKU is used to find a shop item in the 8select-CSE.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| sku | prop\_sku | `string` |

### Examples

```text
827748001
```

## mastersku - prop\_parentSku

The Master-SKU is unique, it contains information about model and color. The Master-SKU ist the main identifier of an item \(parent item\) in a shop.

The Master-SKU is used to create a relation between the parent item and its variants.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| mastersku | prop\_parentSku | `string` |

### Examples

```text
8277480
```

## status - prop\_isInStock

The status provides information about the availability of a variant.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| status | prop\_isInStock | `integer` |

### Examples

in stock

```text
1
```

out of stock

```text
0
```

## model - prop\_model

A model is the basic product. A model can occur in multiple varieties of color and size. Example: the model `Arie` \(8277\) is available in 3 colors: `blue` \(480\), `red` \(481\), `yellow` \(482\) and in 4 sizes: `S` \(01\), `M` \(02\), `L` \(03\), `XL` \(04\). So there are 12 varieties in total. Each of them has a unique item number.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| model | prop\_model | `string` |

### Examples

| model | mastersku | sku |
| :--- | :--- | :--- |
| 8277 | 8277-480 | 8277-480-01 |

## name1 - prop\_name

Regular description of an item as normally used in the product detail view.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| name1 | prop\_name | `string` |

### Examples

```text
Desigual Sweatjacke
```

## kategorie1

Description of item groups as used in the shop navigation

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| kategorie1 | - | `string` |

### Examples

```text
Sweatshirts & -jacken
```

## streich\_preis - prop\_retailPrice

The original price or recommended retail price \(RRP\). In a shop commonly displayed as strikethrough price.

Formatted without currency quotation and with dotted decimal notation.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| streich\_preis | prop\_retailPrice | `string` or `float` with 2 decimal places |

### Examples

```text
80.00
199.39
```

## angebots\_preis - prop\_discountPrice

The price at which an item is sold.

Formatted without currency quotation and with dotted decimal notation.

| Column  product\_feed | Column  property\_feed | Data type |
| :--- | :--- | :--- |
| angebots\_preis | prop\_discountPrice | `string` or `float` with 2 decimal places |

### Examples

```text
69.95
137.50
```

## groesse - prop\_size

Size description of an item.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| groesse | prop\_size | `string` |

### Examples

```text
38
L
32/32
32 L
M-L
```

## marke - prop\_brand

Brandname or product manufacturer.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| marke | prop\_brand | `string` |

### Examples

```text
Desigual
HUGO BOSS
Betty Barclay
```

## farbe - prop\_color

The specific color term of the item.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| farbe | prop\_color | `string` |

### Examples

```text
rot
grün
gelb
schwarz-rot-gold
Burnished Rosè
```

## produkt\_url - prop\_url

Deeplink that links directly to the detail page of a specific variant of an item in the shop.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| produkt\_url | prop\_url | `string` |

### Examples

```text
https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387
https://www.bettybarclay.com/de/vera-mont-cocktail-kleid-21254528.html?farbe=burnished-ros&groesse=38
```

## bilder - images

All available images of a specific variant of an item in highest resolution. Multiple images are separated with a pipe `|`.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| bilder | images | `string` |

### Examples

```text
https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$
https://cdn1.bettybarclay.com/out/pictures/1/Cocktail-Kleid_2_182_21254528_6389.v6.jpg|https://cdn1.bettybarclay.com/out/pictures/3/Cocktail-Kleid_2_182_21254528_6389.v6.jpg|https://cdn1.bettybarclay.com/out/pictures/6/Cocktail-Kleid_2_182_21254528_6389.v6.jpg
```

## beschreibung - prop\_description

The item description text, formatted in HTML.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| beschreibung | prop\_description | HTML `string` |

### Examples

```text
<p>Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.<br><br>    - modisch nach innen gezogenen Seitennähte<br>  - zwei Nahttaschen auf Hüfthöhe<br>  - Rückenteil modisch verlängert<br>  - Rückenlänge bei Gr. S (36): ca. 64 cm<br>  - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm<br><br>    Material: 51% Baumwolle, 45% Polyester, 4% Elasthan<br><br>    ---Pflegehinweise---<br>  - Maschinenwäsche bei 30°, von links<br>  - nicht für den Trockner geeignet<br>
```

## beschreibung1

The item description, formatted as text.

| Column product\_feed | Column property\_feed | Data type |
| :--- | :--- | :--- |
| beschreibung1 | - | `string` |

### Examples

```text
Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.- modisch nach innen gezogenen Seitennähte - zwei Nahttaschen auf Hüfthöhe  - Rückenteil modisch verlängert - Rückenlänge bei Gr. S (36): ca. 64 cm - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm Material: 51% Baumwolle, 45% Polyester, 4% Elasthan ---Pflegehinweise--- - Maschinenwäsche bei 30°, von links - nicht für den Trockner geeignet
```

