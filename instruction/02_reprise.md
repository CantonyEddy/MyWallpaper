Reprends le traitement des wallpapers non encore analysés.

1. Ouvre "wallpapers.md" et récupère la liste des fichiers déjà traités (colonne ancien_nom)
2. Liste tous les fichiers images à la racine (.jpg .jpeg .png .webp .gif .bmp .tiff)
3. Identifie ceux qui ne sont pas encore dans le .md
4. Analyse visuellement chacun des fichiers manquants
5. Ajoute les nouvelles lignes à la suite dans le tableau de "wallpapers.md" en continuant la numérotation des ID, en renseignant les 4 colonnes ID | ancien_nom | nouveau_nom | aperçu
   - La colonne "aperçu" contient une miniature cliquable au format HTML pointant vers le fichier réellement présent sur le disque :
     <a href="FICHIER"><img src="FICHIER" width="120"></a>
     (encode les espaces en %20, les parenthèses en %28/%29 dans le chemin)
6. Affiche les 20 nouvelles lignes ajoutées pour validation
7. Attends ma confirmation avant de renommer quoi que ce soit

RAPPEL DE LA CONVENTION :
FORMAT : catégorie_sujet-détail_couleur-dominante_artiste.extension
- Séparateur entre blocs : underscore _
- Mots composés dans un bloc : tiret -
- Tout en minuscules
- Si artiste inconnu : omets ce bloc
- En cas de doublons (même image en plusieurs résolutions), suffixe le dernier bloc avec -02, -03, etc.

CATÉGORIES (bloc "catégorie") — utilise l'une des suivantes, en crée une nouvelle si besoin :
anime, manga, nature, space, scifi, fantasy, abstract, pixelart, art, cars, gaming,
tech, minimal, aesthetic, pokemon, architecture, halftone.
- architecture : bâtiments, cathédrales, dômes, escaliers, structures, plafonds, etc.
- halftone : rendus en trame de points / demi-teintes (versions "dots"/tramées d'une image).
  Pour ces fichiers, la catégorie est "halftone" (et non la catégorie de l'image d'origine).
  Un éventuel fichier vecteur .svg compagnon porte le même nom de base.
