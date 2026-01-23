# Numérotation des pièces

Une fois toutes les lettres modélisées, nous avons pu voir que le nombre de pièces à découper au laser était assez grand. De plus beaucoup de pièces ont des formes similaires (ex: tous les guides pour les courbes).

Il fallait donc une solution pour qu'une fois toutes les pièces découpées on puisse les identifier facilement.

Nous avons donc choisi de marquer chaque pièce au laser avec le nom de la lettre et un numéro.

Pour se faire, les textes correspondants ont été ajouté en vert dans le document 2D Inkscape. Le vert étant la couleur utilisée au FabLab de Grenoble pour la gravure en surface.

Cependant les calques de textes ne sont pas gérés par le logiciel de découpe/gravure laser, les textes ont donc été converti en tracés.

Plutôt que de simplement convertir les textes en tracés, ce qui aurait transformé le contour des lettres, nous avons choisi d'utiliser une font Hershey adaptée à la gravure.

Pour avoir plus d'infos sur les fonts Hershey et les problèmes qu'elles tentent de résoudre: https://www.evilmadscientist.com/2011/hershey-text-an-inkscape-extension-for-engraving-fonts/

> [!NOTE]
> Les annotations `Textes_hershey` ont été générées depuis le groupe de calques `TO_HIDE/Textes_vector_to_hide` grace à l'extension Inkscape [fablabnbg/inkscape-text2hershey](https://github.com/fablabnbg/inkscape-text2hershey)

> [!WARNING]
> La gravure de texte Hershey étant assez fine, nous avons fait le choix de ne pas nous embêter à orienter les pièces pour avoir la gravure face cachée. Nous pensions que la peinture couvrirait la gravure mais cela n'a finalement pas été le cas et on peut deviner la gravure à travers la peinture. Cela n'est cependant pas trop gênant car les lettres sont faites pour être vues de loin et ça reste assez discret.
