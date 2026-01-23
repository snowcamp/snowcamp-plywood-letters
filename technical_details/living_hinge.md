# Living hinge

Certaines lettres ont des formes arrondies, et dans ce cas il faut une méthode pour que le contreplaqué qui constitue la tranche de la lettre puisse épouser la forme arrondie.

La difficulté vient du fait que contreplaqué utilisé pour ce projet est rigide et donc il n'est pas possible de le courber suffisamment pour épouser les courbes des lettres sans risquer de le casser.

Une première solution avait été identifiée avec les membres du FabLab de Grenoble et consistait à utiliser du contreplaqué cintrable. Ils en avaient à disposition dans le FabLab et m'ont proposé de l'utiliser. Cependant après analyse il s'est avéré que ce contreplaqué comportait une couche interne dans un matériau qui ne pouvait pas passer à la découpeuse laser. Cette solution a été écartée.

Une autre solution adaptée à cette problématique consiste à faire plein de traits de coupe dans le contreplaqué afin de "casser" sa structure et réduire sa rigidité. On parle alors de `Living Hinge`. C'est la solution qui a été choisir pour se projet.

![Image illustrant le principe de Living Hinge](/media/living_hinge_3D.png)

## Choix de la forme du Living Hinge

Lorsqu'on fait du `Living Hinge`, la forme des traits de coupes va avoir un impact direct sur la flexibilité du contreplaqué.

> [!TIP]
> Plusieurs formes de Living Hinge sont décrites dans cet [article internet](https://www.ponoko.com/blog/how-to-make/how-to-design-a-living-hinge/).

La forme choisie pour ce projet est le rectangle:
- Par soucis de simplicité
- Permet d'enlever beaucoup de matière avec peu de traits de coupe
- Jouer sur le nombre et la taille des rectangles permet de trouver le juste équilibre entre la flexibilité finale du matériau et la vitesse de découpe

> [!WARNING]
> La découpe des `Living Hinge` est très chronophage en temps machine.
> Nous étions partis sur des réctangles de 1.5mm de largeur. Cela donnait un matériau très souple, mais le temps de découpe total des `Living Hinge` aurait été de plus de 10h.

> [!TIP]
> Un bon point de départ pour trouver la taille de rectangle idéale est d'utiliser la règle de la section carrée. C'est à dire que la taille des rectangles doit être celle de l'épaisseur du matériau. Ainsi la forme résultante aura une section carrée.
Dans notre cas, le contreplaqué faisant 5mm d'épaisseur, nous avons choisi une largeur de rectangle de 5mm. Le temps de découpe a été divisé par plus de 3, mais la capacité de courbure du contreplaqué restait suffisante pour notre besoin.
Merci au personnel du FabLab qui m'a donné cette astuce

![Image montrant une section de coupe où on peut voir que la section est carrée](/media/living_hinge_carre.png)

## Modélisation du Living Hinge

### Dans OnShape

Pour modéliser le plan de découpe des `Living Hinge`, le premier réflexe a été de le faire dans OnShape.

Pour se faire:
- Définir des variables pour les propriétés du `Living Hinge`:
  - `living_hinge_tab`:
  - `living_hinge_slot_spacing`:
  - `living_hinge_slot_width`:
  - `living_hinge_pattern_distance`:
![Image montrant les paramètres de base du Living Hinge dans OnShape](/media/living_hinge_parameters.png)
- Définir 2 variables pour chaque section courbe des lettres:
  - `distance_curve_XXX`: Une variable de type `Measured` correspondant à la longueur de la pièce soumise au `Living Hinge`
  - `qty_curve_XXX`: Le nombre de lignes de rectangles à créer. Cette variable est calculée selon la formule: `(floor(#distance_curve_XXX/((#living_hinge_slot_spacing+#living_hinge_slot_width)*2)))`
![Image montrant les paramètres du Living Hinge pour la lettre C dans OnShape](/media/living_hinge_letter_parameters.png)
- Créer un sketch sur la surface de la pièce soumise au `Living Hinge`
  - Dessiner les 2 premières lignes de rectangles en utilisant les variables précédemment créées
  ![Image montrant les paramètres de base du Living Hinge dans OnShape](/media/living_hinge_onshape_1.png)
  - Utiliser la fonction `Linear Pattern` pour cloner les 2 premières lignes autant de fois que nécessaires
    - Pour se faire utiliser la variable `qty_curve_XXX` pour définir le nombre de clones et la variable `living_hinge_slot_spacing` pour le nombre de répétitions
    ![Image montrant les paramètres de base du Living Hinge dans OnShape](/media/living_hinge_onshape_2.png)
- Créer une extrusion de type `Remove` sur la surface en utilisant le sketch précédemment créé
![Image montrant les paramètres de base du Living Hinge dans OnShape](/media/living_hinge_onshape_3.png)

Le résultat obtenu fut le suivant:
![Image montrant le modèle 3D OnShape comportant un Living Hinge](/media/living_hinge_onshape.png)

:warning: Le problème de cette méthode est qu'elle demande beaucoup de ressources et de temps de calcul dans OnShape. Pour le projet Snowcamp, la complexité du modèle a été telle qu'il n'a plus été possible d'ouvrir le projet. Nous avons donc décidé de restaurer une version du projet antérieure à la mise en place du `Living Hinge` et à la place de le faire depuis Inkscape.

### Dans Inkscape

Plutôt que de modéliser le `Living Hinge` depuis OnShape, nous avons finalement utilisé Inkscape pour le faire.

L'avantage de cette méthode est qu'elle est beaucoup plus légère en temps de calcul qu'en passant par OnShape.

L'inconvénient de cette méthode est qu'elle doit se faire une fois les fichiers DXF exportés depuis OnShape. Il devient donc difficile d'effectuer une modification dans OnShape et de la répercuter dans Inkscape sans devoir recommencer la génération des `Living hinge`. L'effort reste cependant modéré.

Pour modéliser le `Living Hinge` dans Inkscape, nous avons utilisé le plugin [buxtronix/living-hinge](https://github.com/buxtronix/living-hinge).

Pour se faire:
- Ouvrir le plan de découpe DXF dans Inkscape
- Ouvrir le plugin `living-hinge` depuis le menu `Extensions->Render->Living Hinge...`
- Choisir la forme `Straight lattice` et définir les paramètre de taille des rectangles
- Définir la hauteur et la largeur de la pièce soumise au `Living Hinge`
- Appliquer le changement
- Dans le document Inkscape, déplacer le Path généré pour le superposer à la pièce soumise au `Living Hinge`
- Définir la couleur et l'épaisseur du trait du Path pour qu'il soit perçu correctement par la découpeuse laser (ex: rouge pur et 0.001mm)
- Recommencer pour chaque pièce à courber