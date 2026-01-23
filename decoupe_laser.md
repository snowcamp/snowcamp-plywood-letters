# Découpe laser

Un des aspects cruciaux de ce projet a été la découpe laser des pièces dans le contreplaqué.

Pour cette partie nous avons fait appel aux services du [FabLab de Grenoble](https://lacasemate.fr/fab-lab-et-co/venir-au-fab-lab/) qui mets à disposition des machines et qui avait un personnel disponible pour nous conseiller.

## Fonctionnement du FabLab de Grenoble

Parmi toutes les machines disponibles, le FabLab de Grenoble permet de louer à l'heure 2 découpeuses laser:
- La Trotec Speedy 100 qui permet de découper et graver des surfaces jusqu'à 600x300mm ([plus de détails](https://fablab.lacasemate.fr/#!/machines/trotec-speedy-100-laser))
- La Trotec Speedy 500 qui permet de découper des surfaces jusqu'à 1234x710mm. Ses capacités de gravure sont cependant plus limitées que la Speedy 100 ([plus de détails](https://fablab.lacasemate.fr/#!/machines/trotec-speedy-400-laser))

La location d'une machine est possible après une formation obligatoire à la découpe laser et à condition d'accepter le règlement du FabLab. Un des aspects primordiaux de ce règlement est que les projets effectués au sein du FabLab doivent être documentés et sous licence Creative Commons ([plus de détails](https://fablab.lacasemate.fr/uploads/custom_asset_file/806/charte_fab_lab_la_casemate.pdf)).


## Phase de découpe

La phase de découpe a été la suivante pour chaque plaque de découpe:
- Préparer le fichier Inkscape pour isoler la plaque à découper
- Envoyer l'impression à Job Control
- Installer la plaque de contreplaqué dans la découpeuse laser
- Utiliser les commandes de la découpeuse et celles Job Control aligner le plan de découpe avec la plaque physique telle que posée dans la découpeuse laser
- (optionnel) Positionnement des câles pour plaquer le contreplaqué
- Calibrer la hauteur du laser
- Lancer la découpe et attendre
  - La découpe de chaque plaque a duré entre 15min et 45min selon la présence ou non de `Living Hinge`
- Vérifier que le laser est bien passé à travers les pièces
  - (optionnel) Si ce n'est pas le cas, relancer une découpe identique sans bouger la plaque
- Récupérer les pièces découper, enlever les chutes de contreplaqué de la surface de découpe
- Recommencer pour la plaque suivante

https://github.com/user-attachments/assets/00231377-f477-44a3-b036-b71eb13f9542

https://github.com/user-attachments/assets/0404c598-5a45-49fe-9d6e-897865c9eaed


## Câles et gondolage

Pour la découpe laser nous avons décidé de travailler sur la surface maximum autorisée par la découpeuse laser.

L'avantage de cette approche est qu'il a été plus facile d'optimiser le plan de découpe pour perdre moins de matière.

Cependant l'inconvénient que nous avons découvert au moment de la découpe est que nous avons stocké le contreplaqué dans de mauvaises conditions et que celui-ci a gondolé.

Heureusement le FabLab mets à disposition des petites câles pour plaquer le contreplaqué contre la surface de découpe.

Dans 90% du temps cela a suffi, mais pour 2 plaques le gondolage était tel que nous n'avons pas réussi à suffisamment plaquer les plaques. Nous avons donc dû utiliser le laser pour recouper les plaques en 2 voire 3 puis modifier notre plan de découpe en conséquence.

## Temps de découpe

Le point où nos prévisions ont été le plus faussées est le temps de découpe.

Lorsqu'on regarde une découpeuse laser en action, les mouvements du laser sont très rapides, ce qui donne l'impression de pouvoir découper n'importe quoi très rapidement.

Cependant même si la découpe est effectivement très rapide, notre design était sur des surfaces tellement grandes et avec tellement de traits de découpe que le temps de découpe total a explosé.

Nous avions estimé entre 2h et 3h de découpe, en réalité nous avons mis plutôt entre 6h et 7h, sachant que le personnel du FabLab nous a conseillé entre temps pour optimiser le temps de découpe.

## Odeur et salissures liées au contreplaqué coupé au laser

C'est un détail dans la gestion de ce projet, mais un élément à prendre en compte lors de la découpe laser de contreplaqué, les brulures sur la tranche des pièces découpées ont une odeur forte et sont salissantes.

> [!TIP]
> Il est donc important de prévoir une pièce à part pour stocker les pièces coupées pour ne pas polluer l'air de votre pièce de vie.
> Il est aussi conseillé de mettre des gants pour manipuler ces pièces, au risque d'avoir les mains colorées par le contreplaqué brulé pendant quelques jours.
