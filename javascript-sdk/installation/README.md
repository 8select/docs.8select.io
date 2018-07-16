# Installation

## Funktionsweise des 8select-CSE JavaScript SDK

Das Widget-Loader Script `loader.js` ist eine ca. 5 KB große JavaScript Datei. Dieses Script erzeugt ein FIF \(Friendly IFrame\) in dem die 8select CSE geladen wird.

Diese Technik verhindert das Blockieren von Downloads anderer Ressourcen. Außerdem wird das `onload` Event des Browsers nicht blockiert. Somit beeinflusst das Einbinden der 8select CSE in keinster Weise die Ladezeiten Ihres Shops.

Nachdem das 8select-CSE JavaScript SDK geladen ist, füllt dieses automatisch alle gekennzeichneten div-Elemente mit den entsprechenden Widgets.

