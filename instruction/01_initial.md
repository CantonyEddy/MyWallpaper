Analyse les fichiers images à traiter et renomme-les selon une convention précise, puis range-les par catégorie.

STRUCTURE DU REPO :
- `a_traiter/`  : dossier de dépôt. On y met TOUS les nouveaux wallpapers à traiter, sans distinction (basse ou haute résolution, tout mélangé). C'est la seule source d'entrée.
- `assets/`     : collection finale. Chaque catégorie est un SOUS-DOSSIER (`assets/anime/`, `assets/nature/`, …) pour qu'on puisse télécharger directement la catégorie voulue.
- `wallpapers.md` : catalogue de suivi du renommage.

FICHIERS CIBLES : uniquement les extensions .jpg .jpeg .png .webp .gif .bmp .tiff (et .svg pour les vecteurs compagnons halftone).
Ne touche à aucun autre fichier.

CONVENTION DE NOMMAGE :
FORMAT : catégorie_sujet-détail_couleur-dominante_artiste.extension
- Séparateur entre blocs : underscore _
- Mots composés dans un bloc : tiret -
- Tout en minuscules
- Si artiste inconnu : omets ce bloc
- En cas de doublons (même image en plusieurs résolutions), suffixe le dernier bloc avec -02, -03, etc.

CATÉGORIES (bloc "catégorie" = nom du sous-dossier dans assets/) — utilise l'une des suivantes, en crée une nouvelle si besoin :
anime, manga, nature, space, scifi, fantasy, abstract, pixelart, art, cars, gaming,
tech, minimal, aesthetic, pokemon, architecture, halftone, lofi, marvel, dc, serie,
sport, motivational, humor, horror.
- architecture : bâtiments, cathédrales, dômes, escaliers, structures, plafonds, etc.
- halftone : rendus en trame de points / demi-teintes (versions "dots"/tramées d'une image).
  Pour ces fichiers, la catégorie est "halftone" (et non la catégorie de l'image d'origine),
  puis sujet-détail et couleur-dominante décrivent le rendu tramé. Un éventuel fichier vecteur
  .svg compagnon porte le même nom de base et va dans le même sous-dossier.

DESTINATION : chaque fichier renommé est placé dans `assets/<catégorie>/`.
Exemples :
assets/anime/anime_one-piece_luffy_white_oda.jpg
assets/nature/nature_mountain-sunset_purple.jpg
assets/scifi/scifi_spaceship-cockpit_dark-blue.png
assets/architecture/architecture_st-pauls-cathedral-dome_blue-grey.jpg
assets/halftone/halftone_mount-fuji-clouds_black-white.png

PROCESSUS :
1. Liste tous les fichiers images présents dans `a_traiter/`
2. Analyse visuellement chaque image
3. Renseigne "wallpapers.md" (Markdown) : tableau à 4 colonnes
   ID | ancien_nom | nouveau_nom | aperçu
   - La colonne "aperçu" contient une miniature cliquable au format HTML pointant vers le
     fichier réellement présent sur le disque, dans son sous-dossier de catégorie :
     <a href="assets/CATÉGORIE/FICHIER"><img src="assets/CATÉGORIE/FICHIER" width="120"></a>
     (encode les espaces en %20, les parenthèses en %28/%29 dans le chemin)
4. Affiche les 20 premières lignes pour validation
5. Attends ma confirmation avant de renommer et de déplacer quoi que ce soit
6. Après confirmation : renomme chaque fichier et déplace-le dans `assets/<catégorie>/`
