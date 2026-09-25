# GoodPlaceToGo

Hofläden, Cafés und Restaurants in der Nähe auf einer Karte. Ein Tipp zeigt den nächsten Ort mit Fussweg. DE/EN, kein Tracking, Standort bleibt im Gerät.

Live: **https://richardcervenka111-create.github.io/GoodPlaceToGo/**

## Was sie zeigt

- Grün: Hofladen (`shop=farm`), orange: Café (`amenity=cafe`), rot: Restaurant (`amenity=restaurant`)
- Filter pro Kategorie, Zähler pro Kategorie
- „Nächster Ort“: Standort, Fussweg über routing.openstreetmap.de (FOSSGIS OSRM), Luftlinie als Rückfall
- Name, Küche, Bio, Öffnungszeiten, Adresse, Telefon, Website, Rollstuhl, wenn in OSM erfasst
- „Diesen Ausschnitt laden“ holt die Orte für den aktuellen Kartenausschnitt, auch ausserhalb von Bern

## Daten

Die Orte kommen live aus OpenStreetMap über die Overpass API (`overpass-api.de`, bei Ausfall `overpass.kumi.systems` und `overpass.private.coffee`). Beim Start wird die Stadt Bern mit Umland (46.89–47.01 N, 7.35–7.53 E) geladen und 24 Stunden im Browser zwischengespeichert. Übertragen wird nur der Kartenausschnitt, nie der Standort. Lizenz ODbL, © OpenStreetMap-Beitragende. Karte: OSM-Kacheln. Kartenbibliothek Leaflet 1.9.4, vendored in `assets/leaflet`.

`data.js` ist bewusst leer (`window.POINTS=[]`). Wer einen Offline-Stand will, kann die Overpass-Abfrage aus `index.html` (`nwr["shop"="farm"]`, `nwr["amenity"="cafe"]`, `nwr["amenity"="restaurant"]`, `out center tags`) einmal ausführen und das Ergebnis als `window.POINTS` ablegen; die App zeigt dann diese Punkte, bis jemand einen Ausschnitt neu lädt.

Fehlt ein Ort oder stimmt etwas nicht? Direkt in OpenStreetMap korrigieren, davon haben alle etwas.

## Bärn Kit

Teil von [Bärn Kit](https://richardcervenka111-create.github.io/-brig/): eine HTML-Datei, selbst gehostete OFL-Schrift, Hell- und Dunkelmodus, Tastatur und Screenreader.

## Lizenz

Code MIT. Daten ODbL (OpenStreetMap).
