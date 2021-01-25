# Stammdaten

Um die Produkte sinnvoll in den Widgets darstellen zu können, muss ein Grundstamm an Daten übermittelt werden.

Der Export muss folgendes enthalten

* SKU
  * primärer Identifikator
* Main-SKU bzw. Parent-SKU
  * Information über Produktzusammengehörigkeit der Varianten
* Model
  * Information über Produktzusammengehörigkeit \(zu welchem Produkt gehört diese Variante\)
* Bestand
  * Flag 0/1 oder aktueller Anzahl Bestand
* Größe
* Name
* Preis und Streichpreis
* Deeplink zur Produktvariante
* Bilder
  * Alle verfügbaren Bilder in maximaler Auflösung. Für eine optimale Präsentation mindestens ein freigestelltes Bild.

{% hint style="warning" %}
Um auf unseren Fashion Content Pool zugreifen zu können, sind weitere Daten nötig. Siehe dazu [**Fashion Content Pool**](../fashion-content-pool/).
{% endhint %}

{% file src="../../.gitbook/assets/datenexport-beispiel.csv" caption="Beispiel vollständiger Export" %}

{% file src="../../.gitbook/assets/datenexport-beispiel-preise-bestand.csv" caption="Beispiel gesonderter Preis- und Bestandsupdate" %}

{% hint style="info" %}
Da sich Preise und Bestände sehr häufig ändern, sollte hierfür mehrfach am Tag ein Download verfügbar sein.   
Es ist auch möglich Preis- und Bestandsupdates gesondert von den restlichen Daten bereitzustellen. Siehe **Beispiel gesonderter Preis- und Bestandsupdate**.
{% endhint %}

{% page-ref page="details.md" %}



