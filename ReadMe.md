# <span style="color:#FFFFFF">Installation und Nutzung eines QGIS-Plugins mit gestreamten TIFF-Dateien: Eine Schritt-für-Schritt-Anleitung </span>

Plugin in QGIS Installieren und Nutzen
------------------------

1. **Plugin installieren**.

    https://github.com/user-attachments/assets/9ed8fa1c-de75-4205-99d8-9a9e186064c4

    - Gehe zu "Plugins" > "Manage and Install Plugins".
    - Suche nach "Swiss Locator" und "Swiss Geo Downloader".
    - Drücke "Install".

2. ** Plugin verwenden und gestreamte Daten laden **.

    https://github.com/user-attachments/assets/3416cf93-0b94-4604-9e01-da67e19c0755
    
    - Drücke auf den neuen Knopf "Swiss Geo Downloader" in der  zweiten Symbolzeile.
    - Suche nach dem gwünschten Daten, in unserem Fall "Vegetation height model Lidar NFI".
    - Wähle "File Type" "streamed tiff".
    - Wähle den benötigten Zeitstempel oder "all", falls alle gewünscht sind.
    - Klicke unten rechts auf "Download".

3. **Was ist "streamed tiff"?**

    Ein "streamed tiff", ist ein spezielles Datenformat, das ermöglicht, nur die aktuell benötigten Daten herunterzulade.
    Es wird nie die gesamte Datei geladen, sondern nur der Teil welcher im Moment auf dem Bildschirm Angezeigt wird.



Werte Abfragen und Daten Extrahierung
---------------------------------------

1. **Werte abfragen**.   

    https://github.com/user-attachments/assets/c5879069-4bae-4792-961d-2052331bd1c2

    - Klicke auf das Symbol "Identify Feature".
    - Wähle einen Baum an.
    - Setze "Mode" auf "Top Down" und "View" auf "Table".
    - Identifiziere den Layer mit einem Wert.

2. **Raster Extrahieren**
    
    https://github.com/user-attachments/assets/2a21ea85-afc3-45b5-875e-55f2d949d792

    - Drücke auf "Raster" > "Extraction" > "Clip Raster by Extent"
    - Wähle für den "Input Layer" der Layer auf dem deine Daten existieren.
    - Drücke bei "Clipping extent" auf "set to current map Canvas Extent".
    - Klicke auf "Run".
    - Dadurch wird ein Ausschnitt des Layers an der aktuellen Bildschirmposition erstellt und lokal gespeichert.


3. **Raster Extrahieren in Polygon grössen**

    - Um nur einen bestimmten Abschnitt, der nicht perfekt auf den Bildschirm passt hertunterzuladen.

    https://github.com/user-attachments/assets/383a965e-cd10-4c5f-8de5-f6e01cbcab26

    - Erstelle einen neuen temporären Layer, mit dem Feature "New Temporary Scratch Layer".
    - Wähle den Geometrytyp Polygon und als CRS EPSG:2056 CH1903+/LV95 (für Schweizer Karten).
    - Zeichne mit dem "Add Polygon" Feature den gewünschten Bereich ein.
    - Drücke auf "Raster" > "Extraction" > "Clip Raster by Mask Layer".
    - Wähle erneut den "Input Layer", den erstellten "Mask Layer" und klicke auf "Run".

Abfrage von Zeitständen in QGIS
-----------------------------------

https://github.com/user-attachments/assets/d617b47f-c16f-41e4-945f-afbcc1895e5f


- Falls die Daten eine "temporal property" besitzen, kann durch Klick auf das Uhren-Symbol der Temporal Controller geöffnet werden.
- Um einem Layer eine Zeiteigenschaft zuzuweisen: Rechtsklick auf den Layer > "Properties" > Temporal.


Abfragen und Ansehen von Daten im Webbrowser
-------------------------------------
