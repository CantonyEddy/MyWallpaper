Donne-moi un état des lieux du traitement des wallpapers.

1. Compte le nombre de fichiers images encore en attente dans `a_traiter/`
   (.jpg .jpeg .png .webp .gif .bmp .tiff .svg)
2. Compte le nombre de fichiers rangés dans les sous-dossiers de `assets/<catégorie>/`,
   et donne la répartition par catégorie
3. Ouvre "wallpapers.md" et compte :
   - Le nombre d'entrées du catalogue (lignes du tableau)
   - Le nombre d'entrées dont le fichier existe réellement dans son sous-dossier
   - Les éventuelles entrées dont le fichier est introuvable (à réconcilier)
   - Les fichiers présents dans `assets/` mais absents du catalogue (à cataloguer)
4. Affiche un résumé clair : en attente (a_traiter), traités (assets), catalogués, et un
   pourcentage d'avancement global (traités / (traités + en attente)).
