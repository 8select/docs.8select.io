# Details and examples

{% hint style="info" %}
Values must be in plain text except for description.&#x20;

Some properties are **required**.
{% endhint %}

## Description (beschreibung) - required

The description text for the article. Often used in the shop on the product detail page. HTML format is allowed here.

### Examples

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

## Color (farbe) - required

The exact colour name of the item.

### Examples

```
rot
grün
gelb
schwarz-rot-gold
Burnished Rosè
```

## Category (kategorie1) - required

Description of the article groups. Often used in the shop's navigation and as breadcrumbs. The full category path will work best.

### Examples

```
Herren - Outdoor Bekleidung - Outdoorhosen - Hardshellhosen
Damen - Blusen & Tuniken
Women - Clothes - Skirts
Men - Clothes - Underwear & Nightwear - Sleepwear
```

## Brand (marke) - required

Brand name or manufacturer of an item.

### Examples

```
JP1880
HUGO BOSS
Betty Barclay
Jimmy Choo
Gucci
```

## Heel height (absatzhöhe)

Heel height of shoes with unit of measurement.

### Examples

```
5,5cm
Absatzhöhe in mm: 60
```

## Department (abteilung)

Classification of the assortments according to target groups. Often used in the shop's navigation.

### Examples

```
DOB
HAKA
KIKO
BESPO
Damen
Herren
Kinder
```

## Sleeve length (aermellaenge)

Especially for upper garments, the length of the sleeves.

### Examples

```
normal
extra-lange Ärmel
ärmellos
3/4 Arm
extra kurzer Arm
```

## Specification (auspraegung)

Important information, especially for sports and outdoor activities, which helps to classify the article in the range.

For backpacks, for example, volume `30-55 litres`, for ski poles the size information in units of measurement `160 to 175cm` or for special versions `left-handed`.

### Examples

```
30-55 Liter
Körpergröße 160 bis 175cm
Linkshänder
Rucksackmaße 40 cm x 28 cm x 18 cm
```

## Related items (baukasten)

SKU for a direct link to 1:1 related items. For example for modular suits.\
On top you can provide a [group](details.md#group-gruppe).

### Examples

```
123-456-789
```

## Assortment (bereich)

A shop may allocate products to different assortments.

### Examples

```
Mode
Outdoor
Kosmetik
Trachten
Lifestyle
DIY
```

## Additional description (beschreibung2)

Additional information about the product, technical description, short description or keywords.

### Examples

```
Gewicht=200 g Gewogen=Gr. L/31 Material=100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## Details (detail)

Any details of the article worth mentioning.

### Examples

```
Reißverschluss seitlich am Saum
Brusttasche
Volants
Netzeinsatz
Kragen in Kontrastfarbe
```

## EAN (ean)

Standardised unique material number according to European Article Number (EAN) or Unified Product Code (UPC).

### Examples

```
5027793879236
```

## Features (eigenschaft)

Specially designed for sports and outdoor use notes on the field of application.

### Examples

```
5 °C
Schlafsack geeignet für Temparaturbereich 1 °C bis -16 °C
```

## Colour spectrum (farbspektrum)

The colour spectrum refers to the main colour in the product and allows product sets across different colours from the same spectrum. Often used as a search filter in the shop.

### Examples

```
Schwarz Grau
Braun Beige
Rot
Blau
Gelb Orange
```

## Filling quantity (fuellmenge)

Refers to the quantity of the item's contents, for example in the case of perfume.

### Examples

```
200ml
0,5 Liter
3kg
150 Stück
```

## More features (funktion)

Describes material functions and properties.

### Examples

```
kratzfest
wasserdicht
trocknet schnell
schnelltrocknend
atmungsaktiv
100% UV-Schutz
pflegeleicht
bügelleicht
körperformend
```

## Group (gruppe)

Denotes an identifier for items that directly belong together. You can also add a relation via the [related items](details.md#related-items-baukasten) property.

For example, bikini top "Aloha" and bikini bottom "Aloha" make the product `4242`. Construction jacket "Ernie" and construction trousers "Bert" make the product group `E&B`.

A group can also consist of more than two items, e.g. mix & match group `Hawaii` consists of three bikini tops and two bikini bottoms.

### Examples

```
12345
E&B
Hawaii
Gruppe-9000
```

## Subcategory (kategorie2)

Subcategory used in the shop.

For example the category is "Damen - Blusen & Tuniken" and the subcategory is "Hemdblusen".

### Examples

```
Regenhosen
Hemdblusen
```

## Extra category (kategorie3)

Extra category used in the shop. Either another subcategory or a completely different category used for this item.

For example the category is "Damen - Blusen & Tuniken", the subcategory is "Hemdblusen" and the extra category is "Kurzarmblusen".

Another example: The category is "Men - Clothing - Jackets", the subcategory is "Jackets" and the extra category is "Leather Jackets".

### Examples

```
Kurzarmblusen
Lederjacken
Parkas
Blousons
Freizeit-Hemden
```

## Children's clothing (kiko)

Classification according to target groups specifically for children's ranges. Often used in the shop's navigation.

### Examples

```
mädchen
jungen
baby
kleinkinder
```

## Collar shape (kragenform)

Especially for upper garments, the description of the collar or neckline.

### Examples

```
Rollkragen
V-Ausschnitt
Blusenkragen
Haifischkragen
Rundhalsausschnitt
```

## Material (material)

Material composition of a product.

### Examples

```
98% Baumwolle, 2% Elasthan
100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## Pattern (muster)

### Examples

```
uni
kariert
floral
einfarbig
gestreift
Blumenmuster
einfarbig-strukturiert
```

## Short name (name2)

Often used as a short name in list views - e.g. `Freizeit-Hemd` or for search engine optimization.

### Examples

```
Regenhose
Bluse
```

## Miscellaneous (sonstiges)

Additional item information that cannot be assigned to a specific attribute.

### Examples

```
abgenähte Taschen
Ripstop
Natürlich
Bio
```

## Upper material (obermaterial)

Rudimentarily distinguishes the fabric. Essential material of the article.

Only fabrics with special optical properties are distinguished.

### Examples

```
baumwoll-denim
velourlederoptik
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

## Fit (passform)

In relation to the body shape, is often used for shirts, jackets and suits.

### Examples

```
modern fit
schmal
bequeme Weite
slim-fit
regular-fit
comfort-fit
körpernah
```

## Special article groups (rubrik)

Designates special article groups. Often used in the shop as a search filter or in the navigation.

### Examples

```
Große Größen
Schwangerschaftsmode
Umstandsmode
Stillmode
Übergrößen
```

## Season (saison)

Describes to which season or seasonal collection the item belongs.

### Examples

```
Winter
Sommer
Winter 17
Sommer 2018
HW18/19
```

## Cut (schnitt)

In reference to the form of the article. Is often used for shirts, trousers and shoes.

### Examples

```
Bootcut
gerades Bein
Oversized
spitzer Schuh
knielang
7/8
```

## Series (serie)

Series are used to identify article families or special editions.

### Examples

```
Mountain
Mountain Professional
Expert Line
```

## Sport type (sportart)

Sports in which the article is used.

### Examples

```
Golf
Bergsteigen
Radfahren
Bike
```

## Style (stil)

Style of the article.

### Examples

```
Business
Casual
Ethno
Retro
```

## Exact model (typ)

The exact model designation describes the product type. For example "Desertboot" instead of "Boot" or "Rain trousers" instead of "Trousers".

### Examples

```
Desertboot
Regenhose
Hemdbluse
```

## Closure (verschluss)

Describes closure types of an item.

### Examples

```
Knöpfe
geknöpft
Reißverschluss
Druckknöpfe
Klettverschluss
Haken&Öse
```

## Washing (waschung)

Optical effect of the material, mostly used for denim.

### Examples

```
used
destroyed
bleached
vintage
stone washed
```
