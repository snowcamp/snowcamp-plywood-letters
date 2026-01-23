# Utilisation de contrepoids

Certaines lettres du projet ont des bases décentrées ce qui les rend non stables même sur un sol plat. C'est le cas des lettres P, S et W.

Grace au logiciel OnShape nous avons pu estimer le centre de gravité de chaque pièce pour savoir si ces lettres pouvaient tenir debout ou non.

![Image montrant le centre de gravité pour les lettres S, W et P sans contrepoids](/media/counterweight_theory.png)

Nous avons donc pu voir que pour ces trois lettres (P, S et W) le centre de gravité était très proche du bord de leur base. Ce qui voulait dire que ces lettres devraient pouvoir tenir debout mais qu'une perturbation légère (ex: coup en passant à côté, sol qui tremble) pourrait les faire basculer.

De plus le centre de gravité calculé par OnShape part du principe que la pièce est parfaite sans défaut de montage, sans prendre en compte le poids de la colle, des cure-dents (même si ça devrait être non significatif), ni des disparités dans la densité du contreplaqué.

Nous avons donc décidé de déplacer le centre de gravité grâce à des contre-poids à la base des lettres.

Pour ce faire nous avons prévu des petits boitiers plastiques imprimés en 3D remplis de riz pour augmenter leur poids.

Le choix de l'impression 3D a été fait pour sa simplicité vis à vis de la taille des pièces.

Le choix du riz a été fait par simplicité pour s'en procurer et par manque de connaissances pour nous fournir en matériaux plus adaptés à ce besoin. Aussi le riz a une densité moyenne connue et trouvable sur internet (~720,83 kg/m3), ce qui nous a permis de créer une simulation dans OnShape pour connaitre le nouveau centre de gravité.

Le résultat théorique était donc le suivant:

![Image montrant le déplacement du centre de gravité pour les lettres S, W et P selon s'il y a un contrepoids ou non](/media/counterweight_theory_2.png)
(rouge = sans contrepoids / bleu = avec contrepoids)


## Cales de blocage

Les lettres étant creuses il a été facile de modéliser des boites aux bonnes dimensions pour faire des contrepoids à mettre dedans. Cependant il nous a fallu trouver comment caler ces boites.

Une première solution aurait été de coller les pièces 3D à la base des lettres. Mais au moment de la modélisation nous n'avions pas accès aux matériaux et donc nous n'avions pas de retours sur l'adhérence des colles entre du PLA et du contreplaqué.

Nous avons donc choisi de partir sur un système de calles en contreplaqué placées et collées grâce à des cure dents ([plus de détails](/technical_details/cure_dents.md)).

Ces calles étant de simples rectangles pour créer une surépaisseur au contreplaqué et tenir les contre-poids, il a été rapide de les modéliser et il a été facile de les placer dans le plan de découpe sans prendre trop de place.

## Boites imprimées en 3D

Les boites ont été faites avec une paroi de 2mm, le couvercle est plat et se pose en haut de la boite, le tout est fixé par des vis M3.

Nous sommes arrivés à imprimer les 3 contrepoids des lettres P, S et W en une seule fois malgré quelques erreurs:
- Le contrepoids du P a été imprimé sans `Brim`, la pièce a subi un léger warping qui impacte l'aspect esthétique de la pièce, mais pas le fonctionnel.
- Le contrepoids du S a été imprimé avec un `Brim` et n'a donc pas subit de warping. Cependant le support interne utilisé pour la partie des écrous s'est décollé en cours d'impression. Heureusement l'imprimante s'en est sortie correctement pour imprimer la partie des écrous malgré l'absence de supports.
- Le contrepoids du W a été modifié pour être imprimable sans supports internes et c'était la bonne solution. Cependant nous avons à nouveau oublié de configurer un `Brim` et la pièce a à nouveau subit un léger warping.

Le timelapse suivant montre l'impression des 3 contrepoids P, S et W dans l'ordre respectif:

https://github.com/user-attachments/assets/46e11908-808c-4e7b-af3b-7679988236cd


### Insertion écrous dans impression 3D

Pour avoir un montage facile, les écrous M3 ont été incrusté au moment de l'impression 3D.

Pour se faire, une instruction PAUSE a été mise dans le G-Code depuis l'application Bambu Studio afin que l'impression se mette en pause avant de refermer l'emplacement des écrous.

https://github.com/user-attachments/assets/f5b2d6be-a6ff-407c-b5e3-6ca7360cba76


## Résultats

### Lettre P
<p>
  <img src="../media/counterweight_P_1.jpeg" width="200" />
  <img src="../media/counterweight_P_2.jpeg" width="200" /> 
  <img src="../media/counterweight_P_3.jpeg" width="200" />
  <img src="../media/counterweight_P_4.jpeg" width="200" />
  <img src="../media/counterweight_P_5.jpeg" width="300" />
</p>


### Lettre S

<p>
  <img src="../media/counterweight_S_1.jpeg" width="200" />
  <img src="../media/counterweight_S_2.jpeg" width="200" /> 
  <img src="../media/counterweight_S_3.jpeg" width="200" />
  <img src="../media/counterweight_S_4.jpeg" width="200" />
  <img src="../media/counterweight_S_5.jpeg" width="200" />
  <img src="../media/counterweight_S_6.jpeg" width="300" />
</p>

Vidéo montrant le S sans contrepoids:

https://github.com/user-attachments/assets/618d1d66-fbee-495f-8a6f-4f7f3a9cae69

Vidéo montrant le S avec contrepoids:

https://github.com/user-attachments/assets/567427f4-42d1-4e8d-87c1-5a6eb2b1381a

### Lettre W

<p>
  <img src="../media/counterweight_W_1.jpeg" width="200" />
  <img src="../media/counterweight_W_2.jpeg" width="200" /> 
  <img src="../media/counterweight_W_3.jpeg" width="200" />
  <img src="../media/counterweight_W_4.jpeg" width="200" />
  <img src="../media/counterweight_W_5.jpeg" width="200" />
  <img src="../media/counterweight_W_6.jpeg" width="300" />
  <img src="../media/counterweight_W_7.jpeg" width="300" />
</p>

Vidéo montrant le W avec et sans contrepoids:

https://github.com/user-attachments/assets/5ceb6470-ee98-40be-af27-570aed971b48
