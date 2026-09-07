Reprends le traitement des wallpapers en attente dans le dossier `a_traiter/`.

SOURCE : `a_traiter/` est le dossier de dépôt. Tous les nouveaux wallpapers y sont placés
sans distinction. C'est la seule source à traiter en fonctionnement normal.

1. Liste tous les fichiers images de `a_traiter/` (.jpg .jpeg .png .webp .gif .bmp .tiff .svg)
2. Analyse visuellement chacun d'eux
3. Ajoute les nouvelles lignes à la suite dans le tableau de "wallpapers.md" en continuant la
   numérotation des ID, en renseignant les 4 colonnes ID | ancien_nom | nouveau_nom | aperçu
   - La colonne "aperçu" contient une miniature cliquable au format HTML pointant vers le
     fichier tel qu'il sera dans son sous-dossier de catégorie :
     <a href="assets/CATÉGORIE/FICHIER"><img src="assets/CATÉGORIE/FICHIER" width="120"></a>
     (encode les espaces en %20, les parenthèses en %28/%29 dans le chemin)
4. Affiche les 20 nouvelles lignes ajoutées pour validation
5. Attends ma confirmation avant de renommer et de déplacer quoi que ce soit
6. Après confirmation : pour chaque fichier, renomme-le et déplace-le de `a_traiter/` vers
   `assets/<catégorie>/`. Un fichier correctement traité ne doit plus rester dans `a_traiter/`.

RAPPEL DE LA CONVENTION :
FORMAT : catégorie_sujet-détail_couleur-dominante_artiste.extension
- Séparateur entre blocs : underscore _
- Mots composés dans un bloc : tiret -
- Tout en minuscules
- Si artiste inconnu : omets ce bloc
- En cas de doublons (même image en plusieurs résolutions), suffixe le dernier bloc avec -02, -03, etc.

CATÉGORIES (bloc "catégorie" = nom du sous-dossier dans assets/) — utilise l'une des suivantes,
en crée une nouvelle si besoin :
anime, manga, nature, space, scifi, fantasy, abstract, pixelart, art, cars, gaming,
tech, minimal, aesthetic, pokemon, architecture, halftone, lofi, marvel, dc, serie,
sport, motivational, humor, horror.
- architecture : bâtiments, cathédrales, dômes, escaliers, structures, plafonds, etc.
- halftone : rendus en trame de points / demi-teintes (versions "dots"/tramées d'une image).
  Pour ces fichiers, la catégorie est "halftone" (et non la catégorie de l'image d'origine).
  Un éventuel fichier vecteur .svg compagnon porte le même nom de base et va dans le même sous-dossier.

NOTE DE TRANSITION (à faire une seule fois, à la prochaine maintenance) :
Historiquement les images étaient à plat dans `assets/`. Il peut rester dans les sous-dossiers
d'`assets/` des fichiers jamais catalogués. Lors de la prochaine maintenance, vérifie une
dernière fois l'ensemble d'`assets/` pour combler ces trous dans "wallpapers.md". Une fois cette
vérification faite, on se fie UNIQUEMENT au dossier `a_traiter/` pour les nouveaux ajouts.
