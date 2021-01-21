# Stammdaten

Um die Produkte sinnvoll in den Widgets darstellen zu können, muss ein Grundstamm an Daten übermittelt werden.

Der Export sollte folgendes enthalten

* möglichst alle Produkteigenschaften die verfügbar sind
* aktueller Bestand bzw. ist der Artikel grundsätzlich bestellbar?
* ist der Artikel derzeit im Shop sichtbar?
* SKU
* Name
* Deeplink
* Größe
* andere Varianteneigenschaften wie Farbe, Muster, Länge, etc.
* Preis
* Streichpreis
* Bilder in maximaler Auflösung, für eine optimale Präsentation mindestens ein freigestelltes Bild
* Information über Produktzusammengehörigkeit \(zu welchem Produkt gehört diese Variante\)

{% file src="../../.gitbook/assets/datenexport-beispiel.csv" caption="Beispiel vollständiger Export" %}

{% file src="../../.gitbook/assets/datenexport-beispiel-preise-bestand.csv" caption="Beispiel gesonderter Preis- und Bestandsupdate" %}

{% hint style="info" %}
Da sich Preise und Bestände sehr häufig ändern, sollte hierfür mehrfach am Tag ein Download verfügbar sein.   
Es ist auch möglich Preis- und Bestandsupdates gesondert von den restlichen Daten bereitzustellen. Siehe **Beispiel gesonderter Preis- und Bestandsupdate**.
{% endhint %}

{% page-ref page="details.md" %}



