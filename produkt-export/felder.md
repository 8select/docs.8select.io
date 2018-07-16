# Felder

{% tabs %}
{% tab title="Pflichtfelder" %}
| Spalte product\_feed | Spalte property\_feed | Beispiel | Beschreibung |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| sku | prop\_sku            | 8277387 | Die Sku ist einzigartig, sie enthält Modell, Farbe und Größe |
| mastersku | prop\_parentSku | 8277480 | Master-Sku beinhaltet Modell und Farbe |
| status | prop\_isInStock | 1 | Bestellbarkeit/Status 0 oder 1 \(0 = nicht bestellbar; 1 = bestellbar\) |
| model | prop\_model | 8277 | "Ein Modell bezeichnet das ""Grundprodukt"". ID kann Name oder Nummer sein. Ein Modell kann in mehreren Ausführungen vorkommen, die sich z.B. in Größe, Farbe oder Muster unterschieden.Beispiel: Das Modell ""Arie"" \(1234\) gibt es in den 3 Farben: ""blau"", ""rot"", ""gelb"" \(567\) und in den 4 Größen: ""S"", ""M"", ""L"", ""XL"" \(89\), also 12 Ausführungen. Jede Ausführung hat eine eindeutige Artikelnummer." |
| name1 | prop\_name | Desigual Sweatjacke | Standardbezeichnung für den Artikel so wie er normalerweise in der Artikeldetailansicht genutzt wird. |
| kategorie1 |  | Sweatshirts & -jacken | Bezeichnung der Artikelgruppen, die meist so in der Shopnavigation verwendet werden. |
| streich\_preis | prop\_retailPrice | 80.00 | Streichpreis ohne Währungsangaben und mit Punkt als Dezimaltrenner formatiert |
| angebots\_preis | prop\_discountPrice | 69.95 | Angebotspreis ohne Währungsangaben und mit Punkt als Dezimaltrenner formatiert |
| groesse | prop\_size | 38 | Größenbezeichnung |
| marke | prop\_brand | Desigual | Markenname bzw. Hersteller |
| farbe | prop\_color | rot | Die exakte Farbbezeichnung des Artikels |
| produkt\_url | prop\_url | [https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387](https://www.ambellis.de/desigual-sweatjacke-8277480.html?sku=8277387) | Deeplink: Führt zum Produkt inklusive der Farbe und der Größe \(Variante\). |
| bilder | images | [https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf\_amb\_prod-main-zoom\_xl$](https://ambellis.scene7.com/is/image/ambellis/ext/8277480-01.jpg?$rtf_amb_prod-main-zoom_xl$)\|[https://ambellis.scene7.com/is/image/ambellis/ext/8277480-02.jpg?$rtf\_amb\_prod-main-zoom\_xl$](https://ambellis.scene7.com/is/image/ambellis/ext/8277480-02.jpg?$rtf_amb_prod-main-zoom_xl$) | Alle verfügbaren Artikelbilder der Variante in der höchsten Auflösung. Mehrere Bilder werden mit einem Pipe `|` getrennt. |
| beschreibung | prop\_description | `<p>Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.<br><br>    - modisch nach innen gezogenen Seitennähte<br>  - zwei Nahttaschen auf Hüfthöhe<br>  - Rückenteil modisch verlängert<br>  - Rückenlänge bei Gr. S (36): ca. 64 cm<br>  - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm<br><br>    Material: 51% Baumwolle, 45% Polyester, 4% Elasthan<br><br>    ---Pflegehinweise---<br>  - Maschinenwäsche bei 30°, von links<br>  - nicht für den Trockner geeignet<br>` | Der Beschreibungstext zum Artikel im HTML-Format. |
| beschreibung1 |  | `Diese auffällig gemusterte Sweatjacke von Desigual zeigt sich mit sportiven Raglanärmeln und Kapuze mit Tunnelzug. Ärmelsaum und Saum sind elastisch gestaltet.- modisch nach innen gezogenen Seitennähte - zwei Nahttaschen auf Hüfthöhe  - Rückenteil modisch verlängert - Rückenlänge bei Gr. S (36): ca. 64 cm - unser Model trägt Größe S (36) bei einer Körpergröße von 176 cm Material: 51% Baumwolle, 45% Polyester, 4% Elasthan ---Pflegehinweise--- - Maschinenwäsche bei 30°, von links - nicht für den Trockner geeignet` | Der Beschreibungstext zum Artikel in Text-Format. |
{% endtab %}

{% tab title="Frei Konfigurierbare Felder" %}
|  |  |
| --- | --- |
|  |  |
{% endtab %}
{% endtabs %}

