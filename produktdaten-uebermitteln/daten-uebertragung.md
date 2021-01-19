# Daten Übertragung

Aktuell unterstützen die Übertragung der Daten im Pull-Prinzip über REST API \(8SELECT Spezifikation\) oder Datei Download.

## REST API

* REST API \(Spezifikation auf Anfrage\)
  * unsere Plugins für Shopware, Oxid und JTL-Shop nutzen diese Art der Datenübertragung

## Datei Download

### Protokolle

* File Storage, wie zum Beispiel
  * sFTP
  * AWS S3
* HTTPS

### Format

Wir können die Produktdaten in fast beliebigem Format abrufen. Ideal ist eine Bereitstellung als CSV mit den Daten einer Produktvariante \(SKU\) als Zeile.

{% file src="../.gitbook/assets/datenexport-beispiel.csv" caption="Beispiel CSV" %}

{% hint style="info" %}
Da sich Preise und Bestände sehr häufig ändern, sollte es hierfür mehrfach am Tag ein Download verfügbar sein. Es ist auch möglich Preis- und Bestandsupdates gesondert von den restliche Daten bereitzustellen.
{% endhint %}

