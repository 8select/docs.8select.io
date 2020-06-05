# Datei - Pull Prinzip

Wir können die Produktdaten in fast beliebigem Format via \(s\)FTP / HTTP\(s\) / S3 / \[...\] abrufen.  
Da sich Preise und Bestände sehr häufig ändern, sollte es hierfür mehrfach am Tag ein Download verfügbar sein. Es ist auch möglich Preis- und Bestandsupdates gesondert von den restliche Daten bereitzustellen.

{% hint style="info" %}
Der Export sollte pro Zeile 1 SKU enthalten.
{% endhint %}

Der Export sollte folgendes enthalten

* möglichst alle Produkteigenschaften die verfügbar sind
* aktueller Bestand bzw. ist der Artikel grundsätzlich bestellbar?
* ist der Artikel derzeit im Shop sichtbar?
* SKU
* Deeplink
* Größe
* Bilder in maximaler Auflösung, optimalerweise ein freigestelltes Bild
* Information über Produktzusammengehörigkeit \(zu welchem Produkt gehören die Varianten\)



