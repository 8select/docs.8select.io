# Zusätzliche Felder

| Spalte product\_feed | Spalte property\_feed | Beispiel | Name für Mapping-Dialog | Beschreibung |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| ean | prop\_ean | 5027793879236 | EAN-CODE | Standardisierte eindeutige Materialnummer nach EAN \(European Article Number\) oder UPC \(Unified Product Code\). |
| name2 |  | Regenhosen | ALTERNATIVE ARTIKELBEZEICHNUNG | Oft als Kurzbezeichnung in Listenansichten verwendet \(z.B. ""Freizeit-Hemd""\) oder für Google mit mehr Infos zur besseren Suche |
| kategorie2 |  | Regenhosen | PRODUKTTYP / UNTERKATEGORIE | Verfeinerung der Ebene PRODUKTKATEGORIE  \(z.B. PRODUKTKATEGORIE = Jacken; PRODUKTTYP = Lederjacken, Parkas, Blousons\) |
| kategorie3 |  | Regenhose | UNTERKATEGORIE | Verfeinerung der Ebene |
| bereich |  | Outdoor | BEREICH | Damit können Teilsortimente bezeichnet sein \(z.B. Outdoor, Kosmetik, Trachten, Lifestyle\) |
| rubrik |  | Schwangerschaftsmode | PRODUKTKATEGORIE / -RUBRIK | bezeichnet spezielle Artikelgruppen, die als Filter oder Shop-Navigation genutzt werden \(z.B. Große Größen, Umstandsmode, Stillmode\) |
| abteilung |  | dob | ABTEILUNG | Einteilung der Sortimente nach Zielgruppen \(z.B. Damen, Herren, Kinder, DOB, HAKA, KIKO\) |
| kiko |  | mädchen | KIKO | Speziell für Kindersortimente: Einteilung nach Zielgruppen \(z.B. Mädchen, Jungen, Baby\) |
| typ |  | Regenhosen | PRODUKTTYP / UNTERKATEGORIE | Verfeinerung der Ebene PRODUKTKATEGORIE  \(z.B. PRODUKTKATEGORIE = Boot; PRODUKTTYP = Desertboot\) |
| farbspektrum |  | Schwarz Grau | FARBSPEKTRUM | Farben sind einem Farbspektrum zugeordnet \(z.B. Farbe: Himbeerrot &gt; Farbspektrum: Rot\) |
| absatzhoehe |  | 5,5cm | ABSATZHÖHE | speziell bei Schuhen: Höhe des Absatzes \(Format mit oder ohne Maßeinheit z.B. 5,5 cm oder 5,5\) |
| muster |  | kariert | MUSTER | Farbmuster des Artikels \(z.B. uni, einfarbig, kariert, gestreift, Blumenmuster, einfarbig-strukturiert\) |
| aermellaenge |  | extra kurzer Arm | ÄRMELLÄNGE | speziell bei Oberbekleidung: Länge der Ärmel \(z.B. normal, extra-lange Ärmel, ärmellos, 3/4 Arm\) |
| kragenform |  | Rundhalsausschnitt | KRAGENFORM | speziell bei Oberbekleidung: Beschreibung des Kragens oder Ausschnitts \(z.B. Rollkragen, V-Ausschnitt, Blusenkragen, Haifischkragen\) |
| obermaterial |  | baumwoll-denim | ART OBERMATERIAL | "Unterscheidet rudimentär den ""Stoff"". wesentliches Material des Artikels \(z.B. Wildleder, Denim,  Edelstahl, Gewebe, Strick, Jersey, Sweat, Crash, Boucle,  Grobstrick\) |
| Nur Gewebe mit besonderen optischen Eigenschaften werden unterschieden." |  |  |  |  |
| passform |  | modern fit | PASSFORM | in Bezug auf die Körperform, wird häufig für Hemden, Sakkos und Anzüge verwendet \(z.B. schmal, bequeme Weite, slim-fit, regular-fit, comfort-fit, körpernah\) |
| schnitt |  | knielang | SCHNITT | in Bezug auf die Form des Artikels \(z.B. Bootcut, gerades Bein, Oversized, spitzer Schuh\) |
| waschung |  | bleached | WASCHUNG | optische Wirkung des Materials \(bei Jeans z.B. used, destroyed, bleached, vintage\) |
| stil |  | Casual | STIL | Stilrichtung des Artikels \(z.B. Business, Casual, Ethno, Retro\) |
| sportart |  | Bergsteigen | SPORTART | speziell bei Sportartikeln \(z.B. Handball, Bike, Bergsteigen\) |
| detail |  | Brusttasche | DETAIL | erwähnenswerte Details an Artikeln \(z.B. Reißverschluss seitlich am Saum, Brusttasche, Volants, Netzeinsatz, Kragen in Kontrastfarbe\) |
| auspraegung |  | 30-55 Liter | auspraegung | speziell für Sport und Outdoor. Wichtige Informationen, die helfen, den Artikel in das Sortiment einzuordnen \(Beispiele: bei Rucksäcken: Volumen "30-55 Liter", bei Skistöcken: Größenangaben in Maßeinheit "Körpergröße 160 bis 175cm", Sonderausführungen: "Linkshänder"\) |
| baukasten |  | 100760001 | ZUGEHÖRIGER ARTIKEL | SKU für eine direkte Verbindung zu 1:1  zusammengehörigen Artikeln |
| eigenschaft |  | 5 °C | EIGENSCHAFT / EINSATZBEREICH | speziell für Sport und Outdoor. Hinweise zum Einsatzbereich \(Bsp. Schlafsack geeignet für Temparaturbereich 1 °C bis -16 °C, kratzfest, wasserdicht\) |
| fuellmenge |  | 200ml | FÜLLMENGE / INHALT | bezieht sich auf die Menge des Inhalts des Artikels \(z.B. 200ml, 0,5 Liter, 3kg, 150 Stück\) |
| funktion |  | trocknet schnell\|schnelltrocknend\|atmungsaktiv | FUNKTION | beschreibt Materialfunktionen und -eigenschaften \(z.b. schnelltrocknend, atmungsaktiv, 100% UV-Schutz; pflegeleicht, bügelleicht, körperformend\) |
| gruppe |  | Baukastenanzug James | GRUPPE / BAUKAUSTEN | bezeichnet direkt zusammengehörige Artikel \(z.B. Bikini-Oberteil "Aloha" und Bikini-Unterteil "Aloha" = Gruppe 1002918; Baukasten-Sakko "Ernie" und Baukasten-Hose "Bert" = Gruppe "E&B"\). Dabei können auch mehr als 2 Artikel eine Gruppe bilden \(z.B. Mix & Match: Gruppe "Hawaii" = 3 Bikini-Oberteile können mit 2 Bikini-Unterteilen frei kombiniert werden\) . Die ID für eine Gruppe kann eine Nummer oder ein Name sein. |
| material |  | 100% Nylon \(Ripstop\) mit Gore-Tex-Membran \(PTFE\) | MATERIAL | bezeichnet die genaue Materialzusammensetzung \(z.B. 98% Baumwolle, 2% Elasthan\) |
| saison |  | Winter 17 | SAISON | Beschreibt zu welcher Saison bzw. saisonalen Kollektion der Artikel gehört \(z.B. HW18/19; Sommer 2018; Winter\) |
| serie |  | Mountain | SERIE | Hier können Bezeichnungen für Serien übergeben werden, um Artikelfamilien oder Sondereditionen zu kennzeichnen \(z.B. Expert Line, Mountain Professional\) |
| verschluss |  | Knöpfe | VERSCHLUSS | beschreibt Verschlussarten \(z.B: geknöpft, Reißverschluss, Druckknöpfe, Klettverschluss; Haken&Öse\) |
| beschreibung2 |  | Gewicht=200 g Gewogen=Gr. L/31 Material=100% Nylon \(Ripstop\) mit Gore-Tex-Membran \(PTFE\) | ALTERNATIVER BESCHREIBUNGSTEXT | zusätzliche Informationen zum Produkt, technische Beschreibung, Kurzbeschreibung oder auch Keywords |
| sonstiges |  | abgenähte Taschen, Ripstop | SONSTIGES | zusätzliche Artikelinformationen, die keinem spezifischen Attribut zugeordnet werden können |

