# Tutorial - cloud-optimized GeoTIFF in QGIS importieren

[_en français_](./README.fr.md)

## Plugin in QGIS installieren und nutzen

1. **Plugin installieren**

    https://github.com/user-attachments/assets/9ed8fa1c-de75-4205-99d8-9a9e186064c4

    - Gehe zu `Plugins` > `Manage and Install Plugins`.
    - Suche nach `Swiss Locator` und `Swiss Geo Downloader`.
    - Drücke jeweils `Install` für jedes Plugin.

2. **Plugin verwenden und Daten streamen**

    https://github.com/user-attachments/assets/3416cf93-0b94-4604-9e01-da67e19c0755
    
    - Drücke auf den neuen Knopf `Swiss Geo Downloader` ![](assets/SwissGeoDownloaderIcon.png) in der  zweiten Symbolzeile.
    - Suche nach den gwünschten Daten, beispielsweise `Vegetation height model Lidar NFI`.
    - Wähle `File Type` `streamed tiff`.
    - Wähle den benötigten Zeitstempel oder `all`, falls alle gewünscht sind.
    - Klicke unten rechts auf `Download`.

- **Was ist mit `streamed tiff` gemeint?**

    Die Auswahl `streamed tiff` steht zur Verfügung für *cloud-optimized GeoTIFF*. Dies ist ein spezielles Datenformat, das ermöglicht, die jeweils benötigten Daten zu streamen.
    Dadurch wird Speicherplatz gespart, indem kein Download erfolgt und lediglich der Ausschnitt abgefragt wird, welcher für Anzeige oder Berechnung benötigt wird.



## Werte abfragen und Daten extrahieren

- **Werte abfragen**

    https://github.com/user-attachments/assets/c5879069-4bae-4792-961d-2052331bd1c2

    - Klicke auf das Symbol `Identify Feature` ![](assets/IdentifyFeatureIcon.png) .
    - Wähle einen Baum an.
    - Setze `Mode` auf `Top Down` und `View` auf `Table`.
    - Identifiziere den Layer mit einem Wert.

- **Raster extrahieren für Rechteck-Ausschnitt**

    - [x] Damit kann ein rechteckiger Bereich (z.B. Bildschirmbereich) ausgeschnitten und lokal gespeichert werden.
    
    https://github.com/user-attachments/assets/2a21ea85-afc3-45b5-875e-55f2d949d792
    
    - Drücke auf `Raster` > `Extraction` > `Clip Raster by Extent`
    - Wähle für den `Input Layer` der Layer auf dem deine Daten existieren.
    - Drücke bei `Clipping extent` auf `set to current map Canvas Extent` ![](assets/ClippingExtendIcon.png) .
    - Klicke auf `Run`.
    - Dadurch wird ein Ausschnitt des Layers an der aktuellen Bildschirmposition extrahiert und lokal gespeichert.


- **Raster extrahieren für Polygon-Ausschnitt**

    - [x] Damit kann ein rechteckiger Bereich (z.B. Gemeinde) ausgeschnitten und lokal gespeichert werden.

    https://github.com/user-attachments/assets/383a965e-cd10-4c5f-8de5-f6e01cbcab26

    - Vorbereitung: Falls das benötigte Polygon noch nicht vorliegt
        - Erstelle einen neuen temporären Layer, mit dem Feature `New Temporary Scratch Layer` ![](assets/NewTemporaryScratchLayerIcon.png) .
        - Wähle den Geometrytyp `Polygon` und als CRS `EPSG:2056 CH1903+/LV95` (für Schweizer Karten).
        - Zeichne mit dem `Add Polygon` ![](assets/PolygonIcon.png) Feature den gewünschten Bereich ein.
        - Drücke auf `Raster` > `Extraction` > `Clip Raster by Mask Layer`.
        - Wähle den `Input Layer`, den erstellten `Mask Layer` und klicke auf `Run`.

- **Abfrage von Zeitständen in QGIS**

    https://github.com/user-attachments/assets/d617b47f-c16f-41e4-945f-afbcc1895e5f


    - Sofern für Layer eine `temporal property`![](assets/TemporalIcon.png) definiert ist, kann durch Klick auf das Uhren-Symbol der Temporal Controller geöffnet werden.
    - Um einem Layer eine Zeiteigenschaft zuzuweisen: Rechtsklick auf den `Layer` > `Properties` > `Temporal`.

## Browser und Webb Applikationen

- **LFI Webapp Applikation**

    - [x] Auf der Webseite [LFI Webapp](https://www.lfi.ch/de/karten/vegetationshoehe-oberflaechenmodell) können die Daten auch abgefragt werden.

    https://github.com/user-attachments/assets/bf576dcd-d040-45c0-843f-b645b09e2679

    - Es besteht eine Auswahlmöglichkeit zwischen `LiDAR`, `Stereo` und `Sentinel`-Daten, wobei die Datenqualität in dieser Reihenfolge abnimmt.

- **STAC Browser**

    - [x] Auf der Webseite [STAC Browser](https://data.geo.admin.ch/browser/#) können die Daten ebenso wie mit dem `Swiss Geo Downloader`-Plugin bezogen werden.

    - Um die Suchleiste anzuzeigen, muss zunächst ganz nach unten auf der Seite gescrollt werden.

    https://github.com/user-attachments/assets/32f9e678-dfe9-4a9e-be25-46021c88cf57

    - Die Daten können heruntergeladen und deren Metadaten analysiert werden.

    https://github.com/user-attachments/assets/5ec573e3-18bb-4b2d-9deb-2bfe7a450982


# Mitwirkung

... Mitwirkungsmöglichkeiten und Kontaktangaben einfügen ...

Dies ist eine offene & kollaborative Anleitung. Inputs und Rückmeldungen sind ebenso erwünscht wie Beiträge und Mitwirkung.
