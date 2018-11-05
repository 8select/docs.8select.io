# Examples

## ean - prop\_ean

Unique product number according to the standards of European Article Number \(EAN\) or Unified Product Code \(UPC\).

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| ean | prop\_ean | EAN-Code | `integer` |

### Examples

```text
5027793879236
```

## name2

Often used as short description in list views - for example `Casual shirt` or use more information to improve Google searchability.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| name2 | - | ALTERNATIVE ARTIKELBEZEICHNUNG | `string` |

### Examples

```text
Freizeit-Hemd
```

## kategorie2

Refinement of the level `kategorie`.

For example the category `Bekleidung` and the product type `Jacken`.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| kategorie2 | - | PRODUKTTYP / UNTERKATEGORIE | `string` |

### Examples

```text
Jacken
Blusen
Hemden
```

## kategorie3

Refinement of the level `kategorie` or `kategorie2`.

For example the category `Bekleidung`, the product type `Jacken` and the subcategory `Lederjacken`.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| kategorie3 | - | UNTERKATEGORIE | `string` |

### Examples

```text
Lederjacken
Parkas
Blousons
Freizeit-Hemden
```

## bereich

Used to describe different product sections of a shop.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| bereich | - | BEREICH | `string` |

### Examples

```text
Outdoor
Kosmetik
Trachten
Lifestyle
```

## rubrik

Describes special product sections, which are used as a filter or shop-navigation.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| rubrik | - | PRODUKTKATEGORIE / -RUBRIK | `string` |

### Examples

```text
Große Größen
Schwangerschaftsmode
Umstandsmode
Stillmode
```

## abteilung

Differentiate departments according to target groups.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| abteilung | - | ABTEILUNG | `string` |

### Examples

```text
Damen
Herren
Kinder
DOB
HAKA
KIKO
```

## kiko

Differentiation used for children's assortments specifically.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| kiko | - | KIKO | `string` |

### Examples

```text
mädchen
jungen
baby
```

## typ

Refinement of the level `kategorie`.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| typ | - | PRODUKTTYP | `string` |

### Examples

```text
Desertboot
Regenhosen
```

## farbspektrum

Colors are assigned to a color spectrum.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| farbspektrum | - | FARBSPEKTRUM | \`\` |

### Examples

```text
rot
blau
braun
```

\| Farbe \| Farbspektrum \| \| Himbeerrot \| rot \| \| Lilablassblau \| blau \| \| Erdig \| braun \|

## absatzhoehe

Defines the height of the shoe heel, for shoe assortments specifically.

Formatted with or without metric unit.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| absatzhoehe | - | ABSATZHÖHE | `string` |

### Examples

```text
5,5cm
5,5
```

## muster

Describes the pattern or decorative design of an item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| muster | - | MUSTER | `string` |

### Examples

```text
uni
einfarbig
kariert
gestreift
Blumenmuster
einfarbig-strukturiert
```

## aermellaenge

Describes the length of sleeves of an item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| aermellaenge | - | ÄRMELLÄNGE | `string` |

### Examples

```text
normal
extra-lange Ärmel
ärmellos
3/4 Arm
extra kurzer Arm
```

## kragenform

Describes the kind of collar or neckline of an item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| kragenform | - | KRAGENFORM | `string` |

### Examples

```text
Rollkragen
V-Ausschnitt
Blusenkragen
Haifischkragen
Rundhalsausschnitt
```

## obermaterial

General classification of fabric or material.

Only textiles with distinct optics are differentiated.


| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| obermaterial | - | ART OBERMATERIAL | `string` |

### Examples

```text
baumwoll-denim
Wildleder
Denim
Edelstahl
Gewebe
Strick
Jersey
Sweat
Crash
Boucle
Grobstrick
```

## passform

Describes the fit of an item in terms of body shape, often used with shirts and suits. 

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| passform | - | PASSFORM | `string` |

### Examples

```text
modern fit
schmal
bequeme Weite
slim-fit
regular-fit
comfort-fit
körpernah
```

## schnitt

Describes the cut of an item, in terms of shape. 

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| schnitt | - | SCHNITT | `string` |

### Examples

```text
Bootcut
gerades Bein
Oversized
spitzer Schuh
```

## waschung

Optical effect or look of the fabric.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| waschung | - | WASCHUNG | `string` |

### Examples

```text
used
destroyed
bleached
vintage
```

## stil

Style of the item

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| stil | - | STIL | `string` |

### Examples

```text
Business
Casual
Ethno
Retro
```

## sportart

Specific description for sport items. 

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| sportart | - | SPORTART | `string` |

### Examples

```text
Handball
Bike
Bergsteigen
```

## detail

Noteworthy details of the item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| detail | - | DETAIL | `string` |

### Examples

```text
Reißverschluss seitlich am Saum
Brusttasche
Volants
Netzeinsatz
Kragen in Kontrastfarbe
```

## auspraegung

Important information or characteristics of sport and outdoor items, that help classify the item.

For example `30-55 Liter` volume for backpacks and special versions like `left-handed` or sizes like `160 bis 175cm` for ski poles.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| auspraegung | - | AUSPRÄGUNG | `string` |

### Examples

```text
30-55 Liter
Körpergröße 160 bis 175cm
Linkshänder
```

## baukasten

Direct 1:1 connection with a certain item through its SKU.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| baukasten | - | ZUGEHÖRIGER ARTIKEL | `string` |

### Examples

```text
123-456-789
```

## eigenschaft

Indicates the field of use, for sports and outdoor assortments specifically

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| eigenschaft | - | EIGENSCHAFT / EINSATZBEREICH | `string` |

### Examples

```text
5 °C
Schlafsack geeignet für Temparaturbereich 1 °C bis -16 °C
kratzfest
wasserdicht
```

## fuellmenge

Amount of filling quantity or quantity of contents, for example used for perfume.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| fuellmenge | - | FÜLLMENGE / INHALT | `string` |

### Examples

```text
200ml
0,5 Liter
3kg
150 Stück
```

## funktion

Describes special material funktionality or capacity.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| funktion | - | FUNKTION | `string` |

### Examples

```text
trocknet schnell
schnelltrocknend
atmungsaktiv
100% UV-Schutz
pflegeleicht
bügelleicht
körperformend
```

## gruppe

Describes a custom identifier for items that belong together.

For example: bikini top "Aloha" and a bikini bottom "Aloha" grouped by `4242`, blazer "Ernie" and trousers "Bert" grouped by `E&B`

A group can contain more than just two items. For example, mix & match group `Hawaii` consists of 3 bikini tops and 2 bikini bottoms.


| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| gruppe | - | GRUPPE / BAUKAUSTEN | `string` |

### Examples

```text
12345
E&B
Aloha
Gruppe-9000
```

## material

Describes the exact content of fabric specification of the item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| material | - | MATERIAL | `string` |

### Examples

```text
98% Baumwolle, 2% Elasthan
100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## saison
Describes to what season or seasonal collection the item belongs to.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| saison | - | SAISON | `string` |

### Examples

```text
Winter
Sommer
Winter 17
Sommer 2018
HW18/19
```

## serie
Define here if an item belongs to a certain collection, special edition or product line. 

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| serie | - | SERIE | `string` |

### Examples

```text
Mountain
Mountain Professional
Expert Line
```

## verschluss
Describes the way of garment closure of the item.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| verschluss | - | VERSCHLUSS | `string` |

### Examples

```text
Knöpfe
geknöpft
Reißverschluss
Druckknöpfe
Klettverschluss
Haken&Öse
```

## beschreibung2

Additional product information, technical description, summary or keywords.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| beschreibung2 | - | ALTERNATIVER BESCHREIBUNGSTEXT | `string` |

### Examples

```text
Gewicht=200 g Gewogen=Gr. L/31 Material=100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## sonstiges

Additional information, which couldn't be assigned to a specific attribute.

| Column product\_feed | Column property\_feed | Column Attribut-Mapping | Data type |
| :--- | :--- | :--- | :--- |
| sonstiges | - | SONSTIGES | `string` |

### Examples

```text
abgenähte Taschen
Ripstop
```

