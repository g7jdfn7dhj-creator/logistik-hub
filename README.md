# Logistik-Hub v5.2 — PWA (Lagerlayout-Editor)

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
- Speicherung nur lokal: `lhub.r4.layout` (localStorage + IndexedDB-Spiegel). Service-Worker-Cache `lhub-pwa-v5-2`.
