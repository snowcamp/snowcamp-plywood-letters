# Box joint

Pour l'assemblage des pièces de contreplaqué nous avons opté pour des jointures de type [Box joint](https://en.wikipedia.org/wiki/Box_joint).

Le logiciel OnShape ne permet pas nativement d'automatiser la création de `Box joints` mais des plugins existent pour combler ce manque.

Pour ce projet nous avons utilisé le plugin: [FeatureScript Laser Joint](https://cad.onshape.com/documents/578830e4e4b0e65410f9c34e/w/d04a088a0a8ab8361a2aa65c/e/dfd5effddfd7f2ecce4b0246)

Ce script permet de générer automatiquement les `Box joints` entre plusieurs surfaces sélectionnées. Nous avons paramétré le script pour créer des joints de 1cm de large et avec une `Allowance` de `-0.1mm`.

L'`Allowance` correspond au jeu prévu entre les crénelages des différentes pièces. Dans notre cas nous avons choisi un jeu négatif pour compenser la perte de matière liée à l'épaisseur du laser de la découpeuse laser. Le laser ayant un diamètre de `0.1mm`, le jeu pour compenser est donc de `-0.1mm`.

![Image montrant les paramètres du script Laser Joint dans OnShape](/media/boxjoint_parameters.png)

> [!TIP]
> La flèche à droite du champ `Number of pins` permet de contrôler l'ordre du crénelage entre deux pièces, c'est à dire qu'elle pièce aura la première dent du crénelage.

Un inconvénient de ce plugin est qu'il ne permet de générer des `Box joints` qu'entre deux surfaces planes. Les lettres du logo ayant certains côtés courbes, nous avons dû adapter leur design pour que ces côtés courbes se terminent par une section plane sur au moins 2cm.

La taille de cette section plane varie d'une pièce à l'autre et a été trouvée de façon empirique jusqu'à ce que le FeatureScript accepte de générer le `Box joint`.

> [!WARNING]
> Souvent nous n'avons pu générer un `Box joint` que d'un côté des courbes, l'autre côté restant droit. Dans notre cas nous avons pu nous contenter de cette contrainte, un seul côté en `Box joint` étant suffisant pour aligner la pièce et assurer la structure.

Exemple de surface plane créée sur une des pointes de la lettre M:
![Image montrant le haut de la lettre M qui a été modifié pour avoir un aplat à la fin de la courbe](/media/boxjoint_flatcurve.png)
