# Conception

La conception 3D des lettres en contreplaqué a été faite depuis le logiciel [OnShape](https://www.onshape.com/fr/)

## Vectorisation de notre logo

La première étape a été de partir de notre logo PNG et de le vectoriser dans OnShape.
![Image showing the Snowcamp 2D logo](media/logo_snowcamp.png)

Notre logo avait été créé depuis la police d'écriture [Die Nasty](https://www.dafont.com/die-nasty.font)

La vectorisation a été faite manuellement dans un Sketch depuis OnShape avec le logo PNG pour référence.

Le résultat est le suivant:
![Image showing the Onshape sketch for all logo letters](media/cao_sketch_all.png)

Plus de détails sur la vectorisation du logo et les contraintes techniques rencontrée sont disponibles dans le document [/technical_details/vectorisation.md](/technical_details/vectorisation.md)

## Création du volume

Le logo final doit contenir des lettres de 16 cm de profondeur ([plus de détails](/technical_details/dimensions.md#profondeur-des-lettres)).
 
Pour la mise en volume, nous avons créé une marge de 5mm (épaisseur du contreplaqué) sur tous les bords des lettres dans les sketchs 2D de OnShape.

![Image montrant le sketch avec les 5mm de marges](media/conception_1.png)

Ensuite nous avons utilisé la fonction d'extrusion en 4 temps:
- D'abord toutes les faces avant et arrières
- Ensuite toutes les parois horizontales
- Ensuite toutes les parois verticales
- Enfin toutes les parois courbes

Le faire en 4 temps permet de s'assurer que chaque paroi est extrudée dans une étape différente de ses voisines, ce qui permet d'avoir automatiquement une pièce différente générée pour chaque paroi. Sans cette étape des pièces voisines auraient été perçues comme une seule et même pièce par OnShape.

![Image montrant l'extrusion des faces avant et arrières](media/conception_2.png)
![Image montrant l'extrusion des parois horizontales](media/conception_3.png)
![Image montrant l'extrusion des parois verticales](media/conception_4.png)
![Image montrant l'extrusion des parois courbes](media/conception_5.png)

> [!WARNING]
> Pour permettre l'étape suivante de création des jointures, il est important que toutes les pièces se chevauchent.

## Création des jointures

Pour l'assemblage entre les pièces nous avons créé des jointures de type `Box Joint` ([plus de détails](/technical_details/box_joint.md)).

Le script de création des `Box Joint` a tout généré automatiquement.

![Image montrant la création des Box Joints](media/conception_7.png)

## Gestion des courbes

Les pièces courbes ne sont pas supportées telles quelles par la découpeuse laser. Celle-ci ne peut gérer que des pièces plates car le document d'export utilisé sera en 2D.

Pour permettre leur découpe nous sommes passé par la fonction [Sheet Metal Model](https://www.onshape.com/en/features/sheet-metal) de OnShape.

Au niveau des paramètres nous avons utilisé l'onglet `Thicken` avec une épaisseur de 5mm (épaisseur du contreplaqué).

![Image montrant les paramètres pour la création des Sheet Metals](media/conception_metalmodel_parameters.png)

Le contreplaqué étant rigide, plus tard nous avons créé un `Living Hinge` sur les parois courbes ([plus de détails](/technical_details/living_hinge.md)).

## Support des courbes

Pour les parois courbes, nous n'avons pas souhaité avoir des jonctions de type `Box Joint` sur la partie courbe, nous pensons que cela aurait été disgracieux.

A la place nous avons choisi de faire tenir la paroi courbe en sandwich entre les deux faces arrière et avant.

Pour que la paroi courbe soit tout de même maintenue, un système de gouttière a été mis en place. Ce système consiste en des guides de 5mm d'épaisseur qui seront collé contre les faces avant et arrière et qui serviront de support pour les parois courbes qui viendront en appui contre les guides.

![Image montrant les supports de paroi courbes pour la lettre A](media/conception_8.png)
![Image montrant les supports de paroi courbes intégrés dans la lettre A](media/conception_6.png)

## Alignement des supports des parois courbes

Les supports des parois courbes servent d'appui pour que les parois arrivent à ras des bordures de la lettre. Il est donc important de pouvoir les positionner précisément.

Pour ce faire nous avons prévu des axes de guidages tout le long de ces supports. Ces axes sont des trous prévus à la bonne dimension pour faire passer des cure-dents qui serviront d'axe ([plus de détails](/technical_details/cure_dents.md)).

## Contrepoids

Certaines lettres comme le S, le P et le W ne sont pas suffisamment stables pour tenir toutes seules. Un système de contrepoids a donc été mis en place ([plus de détails](/technical_details/contrepoids.md)).

## Préparation de l'export

Pour pouvoir découper les pièces au laser, nous avons dû créer un plan de découpe en 2D.

Au moment de le faire nous n'avons pas trouvé de solution réellement automatisée et qui prenne en compte les dimensions de la surface de découpe de la découpeuse laser.

Nous avons donc mis en place un système D en mettant toutes les pièces dans un document `Assembly` dans OnShape et en les plaçant à peu près à plat dans des zones modélisées avec les dimensions de la découpeuse laser.

Nous avons fait aussi un travail de réflexion pour optimiser au mieux le positionnement des pièces sur les surfaces de découpe pour économiser la matière.

![Image montrant l'assemblage des pièces à plat en vue de dessus](media/conception_export1.png)

> [!WARNING]
> La fonction `Sheet Metal Model` a découpé certaines courbes là où il ne fallait pas. Nous n'avons pas trouvé comment empêcher ce phénomène, donc à la place dans le document `Assembly` nous avons re-joint ces pièces entre elles. Cela demandera un traitement supplémentaire dans Inkscape plus tard.

Ce qui est important est que les pièces soient correctement positionnées sur les axes X et Y, mais elles n'ont pas besoin d'être alignées sur l'axe Z qui disparaitra à l'export. Les outils de positionnement de OnShape étant limités cela nous a permis de gagner du temps en ignorant cette dimension.

Comme on peut le voir sur cette images, les pièces ne sont pas alignées sur l'axe Z.
![Image montrant l'assemblage des pièces à plat en vue de trois-quarts](media/conception_export2.png)

Une fois ce positionnement fait, nous avons dû créer un document `Drawing` dans OnShape et importer la totalité du document `Assembly` en vue de dessus.
![Image montrant le dessin des pièces en 2D vue de dessus](media/conception_export3.png)

Enfin nous avons pu exporter ce document en format DXF avec le module d'export de OnShape.
![Image montrant les paramètres d'export en DXF de OnShape](media/conception_export_parameters.png)

## Modifications dans Inkscape

Une fois le DXF exporté, nous avons pu l'ouvrir dans Inkscape pour continuer la conception pour la découpe laser.

Les pièces courbes ont été modifiées pour mettre en place un `Living Hinge` ([plus de détails](/technical_details/living_hinge.md)).

Les pièces ont été marquées par des numéros d'identifications à graver ([plus de détails](/technical_details/numerotation_pieces.md)).

Les dessins vectoriels ont été optimisés pour la gravure en passant par l'outil `Extensions > Modify Path > Cleanup Path`. Cela permet de fusionner les différents traits de coupe en un seul path continu afin que la découpeuse laser les traites dans un ordre optimal.

Comme expliqué dans les sections précédentes, la fonction `Sheet Metal Model` a créé des traits de coupe là où il ne fallait pas. Bien que nous ayons re-joint les pièces concernées, les traits de coupes existent encore. Nous avons donc supprimé ces traits depuis le document Inkscape (voir calque `TO_HIDE/Cuts_to_hide`).

Enfin pour finaliser le document pour la découpe nous avons sélectionné tous les traits de coupe puis:
- Nous les avons tous mis à une épaisseur de 0.001mm
- Nous avons mis en rouge tous les traits à couper
- Nous avons mis en bleu tous les traits liés au `Living Hinge`
- Nous avons mis en vert tous les traits de marquage des pièces

## Nest&Cut

Lors de la conférence, un membre de la [scop Alma](https://www.alma.fr/) est venu nous parler de leur application [Nest&Cut](https://nestandcut.com/). Il s'agit d'une application web spécialisée dans le placement automatique de pièces dans un plan de découpe avec l'avantage d'être gratuite pour les associations à but non lucratif.

Une fois la conférence passée nous avons donc testé l'application afin voir si elle nous aurait permis de gagner du temps ou de réduire la quantité de matériaux utilisés.

L'application est assez simple d'utilisation et se passe en 3 étapes:
- L'import des pièces 3D
- La configuration de la taille des plaques et de leur nombre
- La génération et le téléchargement du résultat

Pour l'import des pièces en 3D, depuis OnShape il nous a suffi de sélectionner toutes les pièces et de les exporter au format STEP avec l'option `Export unique parts as individual files` activée. Cela économise donc toute la création d'un `Assembly` comme décrit précédemment, étape qui avait pris plusieurs heures à l'époque ([plus de détails](/conception.md#préparation-de-lexport)).

![Image montrant l'écran d'import des pièces dans Nest&Cut](media/conception_nestcut_1.png)

Pour la configuration de la taille des plaques, nous avons créé une entrée avec les dimensions de nos plaques, défini leur quantité, défini une marge de 5mm au niveau des bords des plaques afin de pouvoir utiliser les cales du FabLab de Grenoble et activé la rotation libre des pièces.

![Image montrant l'écran de configuration des plaques dans Nest&Cut](media/conception_nestcut_2.png)

Nous avons ensuite démarré l'optimisation. Avec la qualité au maximum cela a pris à peu près 5min. Le résultat a ensuite été affiché et nous avons pu télécharger le résultat au format DXF. A partir de ce point il est possible de reprendre notre process dans Inkscape pour préparer la découpe comme décrit précédemment ([plus de détails](/conception.md#modifications-dans-inkscape)).

![Image montrant l'écran de résultat dans Nest&Cut](media/conception_nestcut_3.png)

Le résultat est sans appel:
- Durée du process: 1/4 d'heure avec Nest&Cut contre plusieurs heures avec le process manuel
- Nombre de plaques: 9 plaques avec Nest&Cut contre 11 plaques avec le process manuel, soit à peu près 20% de matériaux économisés

Plan de découpe avec le process manuel:
![Image montrant le plan de découpe avec le process manuel](media/conception_nestcut_4.png)

Plan de découpe généré par Nest&Cut:
![Image montrant le plan de découpe généré par Nest&Cut](media/conception_nestcut_5.png)

Cependant nous avons rencontré les quelques problèmes suivants:
- Comme fonction `Sheet Metal Model` avait découpé certaines courbes là où il ne fallait pas, dans le process manuel nous avions recollé ces pièces ensemble dans le document `Assembly`. Or avec l'export en STEP, ces pièces sont séparées et Nest&Cut n'a pas moyen de savoir qu'elles doivent être réunies.
- La rotation libre permet de gagner beaucoup de place, mais cela rend plus difficile une fois dans Inkscape de rajouter les `Living Hinge` car en plus de les placer en X et Y il faut maintenant leur appliquer une rotation précise.
- L'étape d'identification et numérotation des pièces aurait été plus compliquée car une fois le plan de coupe généré dans Nest&Cut toutes les pièces perdent leur nom (spécificité du format DXF).
- L'optimisation d'espace est tel qu'il aurait été plus compliqué de couper les dernières plaques en plusieurs fois lorsqu'elles avaient gondolé. Cependant la vitesse de génération de Nest&Cut est telle que nous aurions pu regénérer le document facilement.
- 2 pièces de type `Sheet Metal Model` n'ont pas pu être importées dans Nest&Cut et provoquaient une erreur. Pour notre test nous avons remplacé ces 2 pièces par d'autres pièces équivalentes en taille. Nous avons contacté l'équipe pour savoir d'où venait ce bug, nous modifieront ce document une fois la réponse obtenue.

Ces quelques problèmes viennent cependant plus de notre façon de travailler avec OnShape que de Nest&Cut en lui-même.
