# Améliorations

Pendant le design, la découpe, le montage et la peinture des lettres, des erreurs ont été commises et des améliorations ont été imaginées. Voici leur liste en vue d'un prochain projet.

Design:
- Plus discuter en amont avec le personnel du FabLab
  - Certaines erreurs de design ont été vues de justesse avant la découpe en discutant avec eux
- Mieux marquer le sens des pièces
  - Une erreur a été fait sur une des lettres et une pièce a été collée à l'envers. Par chance il est été possible de rattraper l'erreur avec un ciseau à bois sur une autre pièce qui venait contre, mais l'erreur aurait pu être fatale et nous sommes passé à deux doigts de devoir racheter du contreplaqué pour redécouper la lettre
  - Réfléchir à un design pour du contreplaqué de 3mm
    - Le contreplaqué de 5mm prend beaucoup plus de temps à être découpé et à certains endroits le laser n'était pas assez puissant pour passer complètement à travers
    - Le contreplaqué de 3mm est beaucoup plus facile à courber
    - Nous aurions pu avoir des pièces plus légères encore
    - Le prix du matériau et du temps d'accès machine aurait pu être réduit d'1/4 voir d'1/3
    - Pour des lettres de 50cm le contreplaqué de 3mm aurait probablement été assez solide
    - Cependant les tranches étant plus fines, le collage aurait été plus fragile
- Prévoir des guides plus larges pour les courbes
  - Les guides de 1cm de large étaient un peu fragiles. Quatre se sont cassés au total, certains pendant la découpe à cause d'une aspérité dans la structure du contreplaqué, d'autres pendant le transport à vélo
- Casser l'angle des guides pour les courbes
  - Les guides n'offrent aucun jeu au niveau où les tranches courbes des lettres rejoignent une tranche droite, ce qui rend difficile de les positionner. En cassant l'angle des guides cela permet de glisser les tranches courbes le long des glissières plus facilement.
- Améliorer les angles de la lettre S
  - Avec les dents du `Box Joint` les angles du S étaient fragiles au niveau des faces avant et arrière car soutenus par une très petite surface 
- Prévoir un `Living Hinge` plus fin pour le N
  - La courbure du haut-gauche du N est à la limite de ce que peut supporter le contreplaqué avec les dimensions de `Living Hinge` utilisées. Le bois a un peu craqué mais c'est passé de justesse
- Améliorer le design des contrepoids pour être imprimables sans support
  - Actuellement seul le contrepoids du W profite de ces améliorations
- Améliorer les fichiers d'impression pour activer le `Brim` sur chaque pièce

Découpe:
- Travailler sur la surface maximum de la découpeuse laser a été rendu compliqué par le fait que les plaques de contreplaqué ont gondolé. Il a donc fallu plaquer chaque plaque avec le système de câles du FabLab de Grenoble mais pour certaines plaques les forces étaient telles que ce système n'a pas suffi. Il a donc fallu découper ces plaques en plusieurs plus petites plaques et adapter les plans de découpe
  - Prévoir un design avec des marges pour mettre des câles hors du parcours du laser
  - Prévoir un design sur de plus petites surfaces
  - Idéalement prendre du contreplaqué de bonne qualité pour moins gondoler et apporter une attention particulière a ses conditions de stockage en attendant la découpe
  - A noter que la surface maximum étant difficile à transporter, nous avons dû utiliser le monte-charge du bâtiment et nous avons dû exceptionnellement stocker du contreplaqué sur place entre les sessions de découpe. Stocker sur place n'est pas censé être possible, merci au personnel du FabLab d'avoir accepté qu'on le fasse. Une surface plus petite aurait permis de transporter les plaques à vélo (il est compliqué/cher de se garer en voiture vers le FabLab de Grenoble)

Montage:
- Être plus généreux sur la colle
  - Nous n'avons pas mis assez de colle à certains endroits ce qui fait que le contact entre les pièces n'était pas très solide
  - Aussi mettre suffisamment de colle pour que ça déborde aurait permis de combler les jeux et rendre moins visible les jointures
- Prévoir plus de serre-joints (il n'y a jamais assez de serre-joints)
  - Le manque de serre-joints a été le facteur limitant pour le temps de montage. Il n'a pas été possible de coller plus d'une lettre à la fois, voir pour certaines il a fallu les coller en plusieurs étapes.
  - Certaines pièces ont manqué de serre-joints ce qui fait que les angles n'étaient pas complètement plaqués et du jeu était visible sur le résultat final

Peinture:
- Mieux préparer les surfaces
  - Les endroits où du rebouche bois a été utilisé ont été globalement plus propres avec des jointures et empreintes de cure-dents moins visibles
  - Sur certaines pièces la fibre du contreplaqué a été révélée par l'humidité de la peinture. Un meilleur ponçage aurait peut-être atténué ce problème
- Insister sur les angles
  - Les angles des lettres ont des enchainements de face et de tranches du contreplaqué (c'est une composante des [box joints](/technical_details/box_joint.md)). Les tranches ont tendance à absorber plus la peinture et nous n'avons pas assez insisté pour compenser cet aspect. Le résultat est que certaines lettres ont des angles un peu délavés.
- Bien diluer la peinture
  - Beaucoup de temps a été perdu car nous ne diluions pas assez la peinture, nous avons bouché plusieurs fois le pistolet et le résultat n'était pas homogène
- Ne pas mettre le pistolet trop près des surfaces
  - Nous avons créé quelques coulures car nous étions trop près
- Peser le pour et le contre de la peinture au pistolet par rapport à la peinture à la bombe
  - La peinture à la bombe a été beaucoup plus facile, rapide et propre que celle au pistolet. Cependant la peinture à la bombe est beaucoup plus toxique que la peinture à l'eau utilisée avec le pistolet et est plus chère à l'achat
