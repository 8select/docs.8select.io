<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Funktionsweise des 8select-CSE JavaScript SDK](#funktionsweise-des-8select-cse-javascript-sdk)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Funktionsweise des 8select-CSE JavaScript SDK

Das Widget-Loader Script `loader.js` ist eine ca. 5 KB große JavaScript Datei. Dieses Script erzeugt ein FIF (Friendly IFrame) in dem die 8select CSE geladen wird.

Diese Technik verhindert das Blockieren von Downloads anderer Ressourcen. Außerdem wird das `onload` Event des Browsers nicht blockiert. Somit beeinflusst das Einbinden der 8select CSE in keinster Weise die Ladezeiten Ihres Shops.

Nachdem das 8select-CSE JavaScript SDK geladen ist, füllt dieses automatisch alle gekennzeichneten div-Elemente mit den entsprechenden Widgets.
