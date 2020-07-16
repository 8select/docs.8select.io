---
description: Erfahren Sie wie sie die 8select.CSE in einem Shop integrieren können.
---

# 8select Curated Shopping Engine \(CSE\)

Die 8select **Curated Shopping Engine** \(CSE\) macht Ihre individuelle Expertise für Ihre Kunden im Onlineshop sicht- und erlebbar. Aus Ihrem Sortiment werden **dynamische Product Sets** generiert \(z.B. Outfits\) und an den von Ihnen gewünschten Touchpoints ausgespielt.

{% hint style="success" %}
Wie Ihnen unsere Curated Shopping Engine dabei hilft Ihre Expertise skalierbar in Ihren Shop zu bringen erfahren sie auf [8select.com](https://www.8select.com) und in unserem [Hilfe-Center](https://knowledge.8select.com/knowledge/wie-werde-ich-kunde).
{% endhint %}

## Integration in einen Shop

### Plug & Play

Die 8select.CSE kann für **Salesforce Commerce Cloud, Shopware, Oxid** und **JTL-Shop** mittels Plugin integriert werden. Die Plugins finden Sie in den jeweiligen App-Stores der Shopsysteme.

### Manuelle Integration

Die manuelle Integration in einen Shop ist sehr einfach und erfolgt im Shop-Frontend mittels JavaScript SDK und im Backend mit Hilfe unserer REST APIs. Produktdaten können via API und als CSV oder XML via Push oder Pull übermittelt werden.

{% hint style="info" %}
Unsere Kunden haben die 8select.CSE bereits problemlos in **SAP Commerce** und **novomind iShop** integriert.
{% endhint %}

#### Widgets im Shop einbinden

Das 8select.CSE JavaScript SDK bietet alle clientseitigen Funktionen um die 8select-CSE vollständig in eine Webseite einzubinden.

Es ermöglicht die Nutzung des

* SYS-PSV Widget - um ein Produktset für eine SKU anzuzeigen
* SYS-PSV Button - um einen Button mit dem Hinweis auf ein passendes Produktset anzuzeigen
* SYS-ACC Widget - um ergänzende Vorschläge zu einer in den Warenkorb gelegten SKU anzuzeigen
* PSP-PSV Widget - um ein bestimmtes Produktsets anzuzeigen
* PSP-TLV Widget - um eine Liste von Produktsets anzuzeigen
* ELTX-Client - für das CSE Performance-Tracking

Das SDK und die Widgets sind sowohl in Desktop Webbrowsern als auch in mobilen Webbrowsern nutzbar.

#### Verbindung von Shop zur 8select.CSE herstellen

Damit die 8select.CSE mit dem Shop kommunizieren kann, muss über unsere REST API eine Verbindung hergestellt werden.

#### Produktdaten Übermittlung

Voraussetzung für die Befüllung der Widgets mit Inhalten ist eine Anlieferung der Produktdaten Ihres Online-Shops. Die Produktdaten müssen über eine API abrufbar sein.  
Optimal ist eine REST API nach unseren Vorgaben.   
Ein Abfrage von Exporten in Textformat wie zum Beispiel CSV und Übermittlung via HTTP/FTP ist auch möglich, jedoch auf Grund der Geschwindigkeit nicht empfohlen.  
Da über die 8select.CSE Widgets Produktpreise angezeigt werden und Produkte direkt in den Warenkorb gelegt werden können, ist es nötig, dass Preise und Bestände möglichst zeitnah aktualisiert abgerufen werden können.

