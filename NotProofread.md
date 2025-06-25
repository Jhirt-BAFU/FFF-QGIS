# <span style="color:#FFFFFF">Installation et utilisation d'un plugin QGIS avec des fichiers TIFF en streaming : un guide étape par étape</span>

Plugin in QGIS Installer et Utiliser
------------------------

1. **Installer le plugin**.

    https://github.com/user-attachments/assets/9ed8fa1c-de75-4205-99d8-9a9e186064c4

    - Allez dans "Plugins" > "Manage and Install Plugins".
    - Cherchez "Swiss Locator" et "Swiss Geo Downloader".
    - Cliquez sur "Install".

2. **Utiliser le plugin et charger les données en streaming**.

    https://github.com/user-attachments/assets/3416cf93-0b94-4604-9e01-da67e19c0755

    - Cliquez sur le nouveau bouton "Swiss Geo Downloader" dans la deuxième barre d’outils.
    - Recherchez les données souhaitées, dans notre cas "Vegetation height model Lidar NFI".
    - Sélectionnez "File Type" comme "streamed tiff".
    - Sélectionnez le timestamp nécessaire ou "all", si tous sont souhaités.
    - Cliquez en bas à droite sur "Download".

3. **Qu’est-ce qu’un "streamed tiff" ?**

    Un "streamed tiff" est un format de données spécial qui permet de ne télécharger que les données actuellement nécessaires.
    Le fichier entier n’est jamais téléchargé, seulement la portion visible à l’écran.

Interroger des valeurs et extraire des données
---------------------------------------

1. **Interroger des valeurs**.

    https://github.com/user-attachments/assets/c5879069-4bae-4792-961d-2052331bd1c2

    - Cliquez sur l’icône "Identify Feature".
    - Sélectionnez un arbre.
    - Réglez "Mode" sur "Top Down" et "View" sur "Table".
    - Identifiez la couche avec une valeur.

2. **Extraire un raster**

    https://github.com/user-attachments/assets/2a21ea85-afc3-45b5-875e-55f2d949d792

    - Cliquez sur "Raster" > "Extraction" > "Clip Raster by Extent".
    - Sélectionnez comme "Input Layer" la couche contenant vos données.
    - Cliquez sur "set to current map Canvas Extent" pour "Clipping extent".
    - Cliquez sur "Run".
    - Un extrait de la couche à la position actuelle de l’écran sera créé et enregistré localement.

3. **Extraire un raster selon un polygone**

    - Pour télécharger uniquement une section spécifique qui ne s’affiche pas parfaitement à l’écran.

    https://github.com/user-attachments/assets/383a965e-cd10-4c5f-8de5-f6e01cbcab26

    - Créez une nouvelle couche temporaire avec la fonction "New Temporary Scratch Layer".
    - Choisissez le type de géométrie "Polygon" et comme CRS "EPSG:2056 CH1903+/LV95" (pour les cartes suisses).
    - Dessinez la zone souhaitée avec l’outil "Add Polygon".
    - Cliquez sur "Raster" > "Extraction" > "Clip Raster by Mask Layer".
    - Sélectionnez de nouveau le "Input Layer", la "Mask Layer" créée, puis cliquez sur "Run".

Requête de données temporelles dans QGIS
-----------------------------------

https://github.com/user-attachments/assets/d617b47f-c16f-41e4-945f-afbcc1895e5f

- Si les données possèdent une "temporal property", vous pouvez ouvrir le "Temporal Controller" en cliquant sur l’icône horloge.
- Pour attribuer une propriété temporelle à une couche : clic droit sur la couche > "Properties" > "Temporal".

Requête et affichage de données dans le navigateur web
-------------------------------------
