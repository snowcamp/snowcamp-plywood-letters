# Fichiers d'impression 3D

Le but de ce document est de décrire le contenu des fichiers d'impression 3D pour permettre de redécouper des pièces pour les contrepoids du logo de la conférence ([plus de détails](/technical_details/contrepoids.md)).

Les fichiers d'impression 3D sont les suivants:
- [snowcamp_poids_P.3mf](/src/snowcamp_poids_P.3mf): Contrepoids de la lettre P
- [snowcamp_poids_S.3mf](/src/snowcamp_poids_S.3mf): Contrepoids de la lettre S
- [snowcamp_poids_W.3mf](/src/snowcamp_poids_W.3mf): Contrepoids de la lettre W
- [snowcamp_poids_P_lid.3mf](/src/snowcamp_poids_P_lid.3mf): Couvercle du contrepoids de la lettre P
- [snowcamp_poids_S_lid.3mf](/src/snowcamp_poids_S_lid.3mf): Couvercle du contrepoids de la lettre S
- [snowcamp_poids_W_lid.3mf](/src/snowcamp_poids_W_lid.3mf): Couvercle du contrepoids de la lettre W

Ces fichiers sont configurés pour être ouvert dans le logiciel [Bambu Studio](https://bambulab.com/fr-fr/download/studio) et imprimés en PLA avec une imprimante [Bambu Lab P1S](https://eu.store.bambulab.com/fr/products/p1s), bien qu'ils ne présentent aucune contre-indication à être imprimés sur d'autres imprimantes ou d'autres types de filaments.

Ces fichiers contiennent des instructions `PAUSE` pour que l'impression s'arrête le temps d'insérer un écrou M3 nécessaire pour fermer le couvercle ([plus de détails](/technical_details/contrepoids.md#insertion-%C3%A9crous-dans-impression-3d)).

Pour fermer les couvercles il faut:
- 11 écrous M3 Hu (4 pour le P, 4 pour le S, 3 pour le W)
- 11 vis M3 de 12mm

Les sources de ces fichiers sont présentes dans [le document OnShape du projet](https://cad.onshape.com/documents/e505e8593a2fc47bad0547f7/w/a2e19de377bd4450dc694335/e/f0019e91c5ae519defc0f1de?renderMode=6&uiState=696641a15a318394398b9e02).