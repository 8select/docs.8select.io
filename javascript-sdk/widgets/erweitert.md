# Erweitert

## Callbacks

Einige Widgets rufen einen Error-First-Callback bei Erfolg- bzw. Fehlerfall auf. Darüber lässt sich beispielsweise alternativer Inhalt anstelle eines Widgets anzeigen, wenn zum Beispiel gerade kein Produktset für ein bestimmtes Produkt zur Verfügung steht.

## Lazy Loading

Um Widget-Elemente erst zu laden wenn diese im sichtbaren Bereich, oder in einem bestimmten Abstand zum sichtbaren Bereich sind, kann das Attribut `data-load-distance-factor` gesetzt werden.

`data-load-distance-factor` ist optional und kann eine Zahl größer oder gleich `0` sein. Der Wert beschreibt den Faktor, den ein Widget-Element vom unteren sichtbaren Bereich entfernt sein muss, bis es geladen wird. Siehe dazu folgende [Illustration](./#file-wgt-ldr-lazy-load-pdf).

Ist das Attribut nicht gesetzt, so werden alle Widget-Elemente direkt geladen.

Der Wert `0` startet den Ladevorgang des Widgets sobald das Element den unteren sichtbaren Bereich erreicht.

Beim Wert `1` wird der Ladevorgang bereits einen Bildschirmabstand früher gestartet. Je größer der Wert, desto früher wird ein Widget geladen.

```markup
<div data-sku="42" data-8select-widget-id="sys-psv" data-load-distance-factor="1"></div>
```

## Container-Elemente / Überschriften / Erweiterungen

Das Widget kann an beliebiger Stelle im HTML Dokument eingebunden werden. Sie können das Widget also nahtlos in ihr Layout einfügen.

Die 8select Produktsets sind dynamisch, je nach Verfügbarkeit von Artikeln kann es also mehr oder weniger aktive Produktsets geben. Um zu vermeiden, dass Container-Elemente allein stehen bleiben, wenn das spezifizierte Produktset mal nicht mehr Verfügbar ist, sollte das oberste Container-Element initial versteckt sein. Das heißt die Eigenschaft `display` sollte den Wert `none` erhalten. Darüber hinaus **muss** die CSS-Klasse `-eightselect-widget-container` gesetzt sein.

Sobald das Widget sowie das Produktset geladen sind, wird das Container-Element bzw. das Widget eingeblendet.

**Beispiel mit Container-Element**

```markup
<div class="teaserBox -eightselect-widget-container" style="display: none;">
    <h3 class="teaserTitle">Look der Woche</h3>
    <div class="teaserWrapper">
        <div data-8select-widget-id="psp-psv" data-set-id="365"></div>
    </div>
</div>
```

