# Wallpaper Renaming — Prompts Claude Code

## 1. Prompt initial

```
Analyse tous les fichiers images à la racine de ce repo et renomme-les selon une convention précise.

FICHIERS CIBLES : uniquement les extensions .jpg .jpeg .png .webp .gif .bmp .tiff
Ne touche à aucun autre fichier.

CONVENTION DE NOMMAGE :
FORMAT : catégorie_sujet-détail_couleur-dominante_artiste.extension
- Séparateur entre blocs : underscore _
- Mots composés dans un bloc : tiret -
- Tout en minuscules
- Si artiste inconnu : omets ce bloc

EXEMPLES :
anime_one-piece_luffy_white_oda.jpg
nature_mountain-sunset_purple.jpg
scifi_spaceship-cockpit_dark-blue.png

PROCESSUS :
1. Liste tous les fichiers images présents à la racine
2. Analyse visuellement chaque image
3. Crée un fichier "wallpapers.ods" (OpenDocument Spreadsheet) avec 3 colonnes :
   ID | ancien_nom | nouveau_nom
4. Affiche les 20 premières lignes pour validation
5. Attends ma confirmation avant de renommer quoi que ce soit
```

---

## 2. Prompt de reprise

```
Reprends le traitement des wallpapers non encore analysés.

1. Ouvre "wallpapers.ods" et récupère la liste des fichiers déjà traités (colonne ancien_nom)
2. Liste tous les fichiers images à la racine (.jpg .jpeg .png .webp .gif .bmp .tiff)
3. Identifie ceux qui ne sont pas encore dans le .ods
4. Analyse visuellement chacun des fichiers manquants
5. Ajoute les nouvelles lignes à la suite dans "wallpapers.ods" en continuant la numérotation des ID
6. Affiche les 20 nouvelles lignes ajoutées pour validation
7. Attends ma confirmation avant de renommer quoi que ce soit
```

---

## 3. Prompt de suivi d'avancement

```
Donne-moi un état des lieux du traitement des wallpapers.

1. Compte le nombre total de fichiers images à la racine (.jpg .jpeg .png .webp .gif .bmp .tiff)
2. Ouvre "wallpapers.ods" et compte :
   - Le nombre de fichiers déjà analysés (lignes dans le .ods)
   - Le nombre de fichiers déjà renommés (ancien_nom ≠ nouveau_nom et fichier renommé sur disque)
   - Le nombre de fichiers en attente de renommage (dans le .ods mais pas encore renommés)
   - Le nombre de fichiers pas encore analysés (présents à la racine mais absents du .ods)
3. Affiche un résumé clair avec ces 4 chiffres et un pourcentage d'avancement global
```
