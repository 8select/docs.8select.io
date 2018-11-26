# zusaetzliche-felder-beispiele

## ean - prop\_ean

Standardisierte eindeutige Materialnummer nach European Article Number \(EAN\) oder Unified Product Code \(UPC\).

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| ean | prop\_ean | EAN-Code | `integer` |

### Beispiele

```text
5027793879236
```

## name2

Oft als Kurzbezeichnung in Listenansichten verwendet - z.B. `Freizeit-Hemd` oder für Google mit mehr Infos zur besseren Suche.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| name2 | - | ALTERNATIVE ARTIKELBEZEICHNUNG | `string` |

### Beispiele

```text
Freizeit-Hemd
```

## kategorie2

Verfeinerung der Ebene `kategorie`.

Zum Beispiel ist die Kategorie `Bekleidung` und der Produkttyp `Jacken`.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| kategorie2 | - | PRODUKTTYP / UNTERKATEGORIE | `string` |

### Beispiele

```text
Jacken
Blusen
Hemden
```

## kategorie3

Verfeinerung der Ebene `kategorie` bzw. `kategorie2`.

Zum Beispiel ist die Kategorie `Bekleidung`, der Produkttyp `Jacken` und die Unterkategorie `Lederjacken`.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| kategorie3 | - | UNTERKATEGORIE | `string` |

### Beispiele

```text
Lederjacken
Parkas
Blousons
Freizeit-Hemden
```

## bereich

Damit können Teilsortimente bezeichnet sein.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| bereich | - | BEREICH | `string` |

### Beispiele

```text
Outdoor
Kosmetik
Trachten
Lifestyle
```

## rubrik

Bezeichnet spezielle Artikelgruppen, die als Filter oder Shop-Navigation genutzt werden.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| rubrik | - | PRODUKTKATEGORIE / -RUBRIK | `string` |

### Beispiele

```text
Große Größen
Schwangerschaftsmode
Umstandsmode
Stillmode
```

## abteilung

Einteilung der Sortimente nach Zielgruppen.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| abteilung | - | ABTEILUNG | `string` |

### Beispiele

```text
Damen
Herren
Kinder
DOB
HAKA
KIKO
```

## kiko

Einteilung nach Zielgruppen speziell für Kindersortimente.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| kiko | - | KIKO | `string` |

### Beispiele

```text
mädchen
jungen
baby
```

## typ

Verfeinerung der Ebene `kategorie`.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| typ | - | PRODUKTTYP | `string` |

### Beispiele

```text
Desertboot
Regenhosen
```

## farbspektrum

Farben sind einem Farbspektrum zugeordnet.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| farbspektrum | - | FARBSPEKTRUM | \`\` |

### Beispiele

```text
rot
blau
braun
```

\| Farbe \| Farbspektruk \| \| Himbeerrot \| rot \| \| Lilablassblau \| blau \| \| Erdig \| braun \|

Speziell bei Schuhen die Höhe des Absatzes.

Format mit oder ohne Maßeinheit.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| absatzhoehe | - | ABSATZHÖHE | `string` |

### Beispiele

```text
5,5cm
5,5
```

## muster

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| muster | - | MUSTER | `string` |

### Beispiele

```text
uni
einfarbig
kariert
gestreift
Blumenmuster
einfarbig-strukturiert
```

## aermellaenge

Speziell bei Oberbekleidung die Länge der Ärmel.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| aermellaenge | - | ÄRMELLÄNGE | `string` |

### Beispiele

```text
normal
extra-lange Ärmel
ärmellos
3/4 Arm
extra kurzer Arm
```

## kragenform

Speziell bei Oberbekleidung die Beschreibung des Kragens oder Ausschnitts.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| kragenform | - | KRAGENFORM | `string` |

### Beispiele

```text
Rollkragen
V-Ausschnitt
Blusenkragen
Haifischkragen
Rundhalsausschnitt
```

## obermaterial

Unterscheidet rudimentär den Stoff. Wesentliches Material des Artikels.

Nur Gewebe mit besonderen optischen Eigenschaften werden unterschieden.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| obermaterial | - | ART OBERMATERIAL | `string` |

### Beispiele

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

In Bezug auf die Körperform, wird häufig für Hemden, Sakkos und Anzüge verwendet.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| passform | - | PASSFORM | `string` |

### Beispiele

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

In Bezug auf die Form des Artikels.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| schnitt | - | SCHNITT | `string` |

### Beispiele

```text
Bootcut
gerades Bein
Oversized
spitzer Schuh
```

## waschung

Optische Wirkung des Materials.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| waschung | - | WASCHUNG | `string` |

### Beispiele

```text
used
destroyed
bleached
vintage
```

## stil

Stilrichtung des Artikels.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| stil | - | STIL | `string` |

### Beispiele

```text
Business
Casual
Ethno
Retro
```

## sportart

Konkrete Beschreibung speziell bei Sportartikeln. \(z.B. \) \|

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| sportart | - | SPORTART | `string` |

### Beispiele

```text
Handball
Bike
Bergsteigen
```

## detail

Erwähnenswerte Details an Artikeln.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| detail | - | DETAIL | `string` |

### Beispiele

```text
Reißverschluss seitlich am Saum
Brusttasche
Volants
Netzeinsatz
Kragen in Kontrastfarbe
```

## auspraegung

Speziell für Sport und Outdoor wichtige Informationen, die helfen, den Artikel in das Sortiment einzuordnen.

Bei Rucksäcken zum Beispiel Volumen `30-55 Liter`, bei Skistöcken die Größenangaben in Maßeinheit `160 bis 175cm` oder bei Sonderausführungen `Linkshänder`.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| auspraegung | - | AUSPRÄGUNG | `string` |

### Beispiele

```text
30-55 Liter
Körpergröße 160 bis 175cm
Linkshänder
```

## baukasten

SKU für eine direkte Verbindung zu 1:1 zusammengehörigen Artikeln.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| baukasten | - | ZUGEHÖRIGER ARTIKEL | `string` |

### Beispiele

```text
123-456-789
```

## eigenschaft

Speziell für Sport und Outdoor Hinweise zum Einsatzbereich.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| eigenschaft | - | EIGENSCHAFT / EINSATZBEREICH | `string` |

### Beispiele

```text
5 °C
Schlafsack geeignet für Temparaturbereich 1 °C bis -16 °C
kratzfest
wasserdicht
```

## fuellmenge

Bezieht sich auf die Menge des Inhalts des Artikels, zum Beispiel bei Parfum.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| fuellmenge | - | FÜLLMENGE / INHALT | `string` |

### Beispiele

```text
200ml
0,5 Liter
3kg
150 Stück
```

## funktion

Beschreibt Materialfunktionen und -eigenschaften.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| funktion | - | FUNKTION | `string` |

### Beispiele

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

Bezeichnet einen Identifikator für direkt zusammengehörige Artikel.

Zum Beispiel Bikini-Oberteil "Aloha" und Bikini-Unterteil "Aloha" - Gruppe `4242` Baukasten-Sakko "Ernie" und Baukasten-Hose "Bert" - Gruppe`E&B`.

Dabei können auch mehr als 2 Artikel eine Gruppe bilden z.B. Mix & Match: Gruppe `Hawaii` besteht aus 3 Bikini-Oberteilen und 2 Bikini-Unterteilen.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| gruppe | - | GRUPPE / BAUKAUSTEN | `string` |

### Beispiele

```text
12345
E&B
Aloha
Gruppe-9000
```

## material

Bezeichnet die genaue Materialzusammensetzung des Artikels. \(z.B. \)

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| material | - | MATERIAL | `string` |

### Beispiele

```text
98% Baumwolle, 2% Elasthan
100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## saison

Beschreibt zu welcher Saison bzw. saisonalen Kollektion der Artikel gehört.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| saison | - | SAISON | `string` |

### Beispiele

```text
Winter
Sommer
Winter 17
Sommer 2018
HW18/19
```

## serie

Hier können Bezeichnungen für Serien übergeben werden, um Artikelfamilien oder Sondereditionen zu kennzeichnen.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| serie | - | SERIE | `string` |

### Beispiele

```text
Mountain
Mountain Professional
Expert Line
```

## verschluss

Beschreibt Verschlussarten eines Artikels.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| verschluss | - | VERSCHLUSS | `string` |

### Beispiele

```text
Knöpfe
geknöpft
Reißverschluss
Druckknöpfe
Klettverschluss
Haken&Öse
```

## beschreibung2

Zusätzliche Informationen zum Produkt, technische Beschreibung, Kurzbeschreibung oder auch Keywords.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| beschreibung2 | - | ALTERNATIVER BESCHREIBUNGSTEXT | `string` |

### Beispiele

```text
Gewicht=200 g Gewogen=Gr. L/31 Material=100% Nylon (Ripstop) mit Gore-Tex-Membran (PTFE)
```

## sonstiges

Zusätzliche Artikelinformationen, die keinem spezifischen Attribut zugeordnet werden können.

| Spalte product\_feed | Spalte property\_feed | Spalte Attribut-Mapping | Datentyp |
| :--- | :--- | :--- | :--- |
| sonstiges | - | SONSTIGES | `string` |

### Beispiele

```text
abgenähte Taschen
Ripstop
```

