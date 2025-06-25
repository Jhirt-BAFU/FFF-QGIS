# <span style="color:#FFFFFF">Installation und Nutzung eines QGIS-Plugins mit gestreamten TIFF-Dateien: Eine Schritt-für-Schritt-Anleitung </span>

Plugin in QGIS Installieren und Nutzen
------------------------

1. **Plugin installieren**.

    https://github.com/user-attachments/assets/9ed8fa1c-de75-4205-99d8-9a9e186064c4

    - Gehe zu "Plugins" > "Manage and Install Plugins".
    - Suche nach "Swiss Locator" und "Swiss Geo Downloader".
    - Drücke "Install".

2. **Plugin Brauchen und Streamen**.

    https://github.com/user-attachments/assets/3416cf93-0b94-4604-9e01-da67e19c0755
    
    - Drücke auf den neuen Knopf "Swiss Geo Downloader" in der 2. Zeile.
    - Suche deine gwünschten Daten, in unserem Fall "Vegetation height model Lidar NFI".
    - Wähle file type "streamed tiff".
    - Den Timestamp der gebraucht wird oder "all".
    - Unten rechts auf "Download".

3. **Was ist Streamed Tiff?**

    Ein Streamed Tiff, ist eine spezielles Daten-Format, welches erlaubt, dass nur die benötigten daten heruntergeladen werden. Dabei wird nie die ganze Datei heruntergeladen, sondern dynamisch nur der Teil der gerade Angezeigt wird.



Werte Abfragen und Daten Extrahierung
---------------------------------------

1. **Werte Abfragen**.   

    https://github.com/user-attachments/assets/c5879069-4bae-4792-961d-2052331bd1c2

    <!---
    Add more steps
    -->
    - Um einen bestimmten Wer t zu extrahieren, ist es wichting durch die verschiedenen Layer durchzugehen.

2. **Raster Extrahieren**
    
    https://github.com/user-attachments/assets/2a21ea85-afc3-45b5-875e-55f2d949d792

    - Drücke auf "Raster" > "Extraction" > "Clip Raster by Extent"
    - Wähle für den "Input Layer" der Layer auf dem deine Daten existieren.
    - Drücke bei "Clipping extent" auf "set to current map Canvas Extent"
    - Drücke "Run".
    - Dies wird nun einen Clip machen von dem Layer am Ort wo dein Bildschirm ist, und diese Daten auch effektiv auf dein Gerät Hertunerladen.


3. **Raster Extrahieren in Polygon grössen**

    - Um nur einen bestimmten Abschnitt, der nicht perfekt auf den Bildschirm passt Hertunterzuladen.

    https://github.com/user-attachments/assets/383a965e-cd10-4c5f-8de5-f6e01cbcab26

    - Drücke auf "New Temporary Scratch Layer"
    - Wähle den Geometry Type Polygon und Wählen sie das gegebene CRS, bei der Schweizer Karte ist dies "EPSG:2056 CH1903+/LV95"
    - Drücke nun auf das Add Polygon Feature, und Umkreise den Ort der heruntergeladen werden soll.
    - Drücke auf "Raster" > "Extraction" > "Clip Raster by Mask Layer"
    - Wähle wieder den gegebenen "Input Layer", dein "Mask Layer" und drücke auf "Run"

Abfrage von Zeitsänden in QGIS
-----------------------------------

https://github.com/user-attachments/assets/d617b47f-c16f-41e4-945f-afbcc1895e5f


- Falls die Daten eine "Temporal Property" besitzt, kann man mit einem Click auf das Uhr Icon einen "Temporal Controller" öffnen.


Abfragen und Ansehen von Daten im Webbrowser
-------------------------------------
