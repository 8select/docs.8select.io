# Datenübermittlung

Die Produktdaten können aktuell nur mittels einer vom Shop bereitgestellten REST API im Pull Prinzip übertragen werden.

Die 8select.CSE benötigt die Produktdaten aus dem Shop um Content in Form von Widgets ausspielen zu können.  
Die CSE Widgets stellen Produkte aktuell nur mit einer Variantendimension dar. Dazu muss die CSE vom Kunden konfiguriert werden. Für die Konfiguration muss die CSE alle Produkteigenschaften kennen und von allen Eigenschaften wissen ob diese im Shop für die Variantenbildung genutzt werden oder nicht.  
Um die Abfragen möglichst einfach und performant zu halten, muss ein Shop 3 Endpunkte bereitstellen über den Informationen abgefragt werden können.

* Endpunkt zur Abfrage von Produkten
* Endpunkt zur Abfrage von allen vorhandenen Produkteigenschaften - ohne Werte
* Endpunkt zur Abfrage von allen Produkteigenschaften die der Shop für die Variantenbildung nutzt

## 

