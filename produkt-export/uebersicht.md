# Übersicht

Voraussetzung für die Befüllung der Widgets mit Inhalten ist eine Anlieferung der Produktdaten des Online-Shops an eine von 8select bereitgestellte Standard-Schnittstelle. Die Produktdaten müssen in einem entsprechenden CSV-Format regelmäßig auf einem von 8select zur Verfügung gestellten AWS S3 Bucket abgelegt werden.

Hierbei werden zwei Arten von Anlieferung unterschieden:

* Stammdaten-Feed: Alle Produkte mit allen angeforderten Attributen sowie Bild-URLs - Anlieferung 1x täglich
* Update-Feed: Aktuelle Werte für Preis, Verfügbarkeit und ausgewählte Attribute der Produkte sowie Bilder - Anlieferung alle X Minuten und wenn möglich nur ein Delta

## Format

* Produktvarianten dürfen nur auf Größe basieren, alles andere z.B. Farben muss in Virtuelle Elternprodukte überführt werden.
* Im Export sind ausschließlich Produktvarianten enthalten. Elternprodukte und ggf. Virtuelle Elternprodukte werden nur für die Gruppierung von Varianten via `mastersku` und `model` benötigt.
* Gibt es mehrere Größen definierende Eigenschaften, so müssen diese im Export berücksichtigt werden \(Größe, Länge, Inhalt\).
* Mehrfachnennung im Feldinhalt mit Pipe `|` trennen, keine extra Leerzeichen einfügen - z.B. für ein Mehrfarbiges Shirt: Farbe `schwarz|rot|gold`
* CSV-Trennzeichen Semikolon `;`
* CSV-Text-Qualifier Doppelte-Anführungszeichen `"`

## AWS S3

* Upload auf ein S3 Bucket
* Upload erfolgt mit Credentials
* ACL für die Datei muss auf bucket-owner-full-control gestellt sein
* Bucket: s3://productfeed.8select.io/

### Dateipfad

```text
<bucket>/<feed_id>/<feed_type>/<year>/<month>/<day>/<feed_id>_<feed_type>_<timestamp>.csv
```

* feed\_id = Feld “Feed ID” aus Plugin Konfiguration
* feed\_type
  * täglicher Stammdatenexport = product\_feed
  * Preis, Statusupdates und Updates ausgewählter Attribute sowie Bilder = property\_feed
* year = das aktuelle Jahr im Format yyyy - z.B. 2018 \(UTC\)
* month = der aktuelle Monat im Format mm - z.B. 05 \(UTC\)
* day = der aktuelle Tag im Format dd - z.B. 07 \(UTC\)
* timestamp = unix timestamp in Millisekunden - z.B. 1515147815000 \(UTC\)

