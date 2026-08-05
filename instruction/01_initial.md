Analyse tous les fichiers images à la racine de ce repo et renomme-les selon une convention précise.

FICHIERS CIBLES : uniquement les extensions .jpg .jpeg .png .webp .gif .bmp .tiff
Ne touche à aucun autre fichier.

CONVENTION DE NOMMAGE :
FORMAT : catégorie_sujet-détail_couleur-dominante_artiste.extension
- Séparateur entre blocs : underscore _
- Mots composés dans un bloc : tiret -
- Tout en minuscules
- Si artiste inconnu : omets ce bloc
- En cas de doublons (même image en plusieurs résolutions), suffixe le dernier bloc avec -02, -03, etc.

EXEMPLES :
anime_one-piece_luffy_white_oda.jpg
nature_mountain-sunset_purple.jpg
scifi_spaceship-cockpit_dark-blue.png

PROCESSUS :
1. Liste tous les fichiers images présents à la racine
2. Analyse visuellement chaque image
3. Crée un fichier "wallpapers.md" (Markdown) contenant un tableau à 4 colonnes :
   ID | ancien_nom | nouveau_nom | aperçu
   - La colonne "aperçu" contient une miniature cliquable au format HTML pointant vers le fichier réellement présent sur le disque :
     <a href="FICHIER"><img src="FICHIER" width="120"></a>
     (encode les espaces en %20, les parenthèses en %28/%29 dans le chemin)
4. Affiche les 20 premières lignes pour validation
5. Attends ma confirmation avant de renommer quoi que ce soit
