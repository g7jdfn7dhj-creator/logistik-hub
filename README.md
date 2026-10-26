# Logistik-Hub v5.3 — PWA (Lagerlayout-Editor)

## Neu in v5.3
- **Hallenhöhe**: Feld + Schieberegler im Raum-Tab (leer = Anzeige mit 7 m, nicht gespeichert). Wände und Decke im 3D folgen dem Wert, auch live über „3D-Vorschau“. Der 2D-Plan zeigt ein Höhen-Badge `H = x,x m` und eine Seitenansicht mit den Höhen von Regalen, Trennwänden und Objekten. Regale, Trennwände und Objekte, die höher als die Halle sind, werden als Fehler gemeldet und blockieren das Speichern. Die Höhe ist in Rückgängig, JSON-Export/-Import, Backup und Migration enthalten (alte Layouts: leer).
- **LKW-Einfahrt**: Der LKW fährt durch das (auf 5,4 m verbreiterte) Tor in die Halle, hält neben der verknüpften Entladefläche (im Tor wählbar, sonst die nächste), wird darauf entladen und fährt wieder hinaus. Ist die Halle zu niedrig (< 4,5 m) oder fehlt ein Fahrweg, warnt der Editor und der LKW entlädt wie bisher am Tor.

Gegenüber v5.1 neu: **Lagerlayout-Editor** (Parameter → „Lagerlayout bearbeiten“ bzw. Hinweis im leeren Lager).

- **Raum:** Rechteck (Länge × Breite), Quadrat, Kreis (Durchmesser) oder beliebige Form (Eckpunkte „x;y“ eingeben oder auf dem Plan zeichnen). Alle Maße in Metern, nichts ist vorbelegt.
- **Lagerart:** nur Regale, nur Flächen/Zonen oder gemischt.
- **Objekte:** Regale (automatisch nummeriert R1, R2 …, umbenennbar; Fächer, Ebenen, Fachbreite, Tiefe, Bedienseite), Flächen/Zonen (F1, F2 …; Breite × Tiefe), Tore Wareneingang (T…), Ausgänge zur Produktion (A…; rasten an der Wand ein).
- **Entladeflächen** (E1, E2 …): eigene 3D-Darstellung (Epoxid-Platte, Bordstein mit Gelb-Schwarz-Warnstreifen, Ecken-/Randmarkierung, Schablonenschrift „E1“) und eigenes 2D-Symbol; Lagerort `E<Nr>`.
- **Trennwände** (W1 …): auf dem Plan zeichnen (Start/Ende mit Raster) oder Länge, X/Y, Drehung eingeben; Höhe optional (leer → Darstellung 2,2 m); optionale Tür/Öffnung (Breite, Position). Kollisions-/Raumprüfung; Stapler und Logistiker gehen nur durch Öffnungen.
- **Lagerorte:** Regal `R<Nr>-<Fach>-<Ebene>` (z. B. `R1-05-2`), Fläche `F<Nr>`, Entladefläche `E<Nr>`.
- **Editor:** 2D-Draufsicht mit Raster/Einrasten, Verschieben (Maus/Touch), Drehen, Duplizieren, Löschen, Zahlenfelder, Kollisions- und Außerhalb-Prüfung, Rückgängig/Wiederholen, Speichern/Abbrechen, Export/Import JSON.
- **Prozess (nur manuell):** Regeln Teil / Teilegruppe (Präfix) / Tor → Ziel-Regal/-Fläche, Anliefertor, Auslagerweg (Ausgang); Einlagerreihenfolge. Wirkt als Lagerort-Vorschlag bei der Eingabe und steuert LKW-Tor und Weg der Logistiker in der Animation. Daten werden nie automatisch verschoben.
- **3D** wird aus dem gespeicherten Layout aufgebaut; Stapler und Logistiker laufen über ein Wegeraster um die Regale herum.
- **Migration:** bestehende Installationen (v5.1) erhalten ihre feste Halle (4 × 20 × 3 = 240 Plätze) als bearbeitbares Layout; alle Lagerorte bleiben gültig. Neue Installationen starten ohne Layout.
- Speicherung nur lokal: `lhub.r4.layout` (localStorage + IndexedDB-Spiegel). Service-Worker-Cache `lhub-pwa-v5-3`.
