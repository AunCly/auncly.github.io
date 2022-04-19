---
layout: post
title:  "CodinGame - Music Score"
categories: [ Dev ]
image: assets/images/posts/music-scores/main.jpg
comments: false
excerpt: Résolution du puzzle de CodinGame "Music Score"
---

## Avant de commencer

Je ne vais pas partager de code lors de cet article pour éviter qu'il ne se retrouve copié/collé tel quel sur la plateforme. Je vais seulement expliquer comment j'en suis venu à bout, étape par étape. Si vous avez des questions, n'hésitez pas à me contacter sur Twitter ou via le formulaire de contact de ce site.

## Énoncé

Votre mission est d'aider Doctor Who à terrasser le Graske. Pour ce faire, vous devez implémenter une interface qui peut lire directement des partitions scannées et les transformer en notes de musique.  
Les partitions sont relativement simples et sont composées uniquement de blanches et de noires. Les notes sont représentées sur une portée et sont limitées aux notes suivantes (blanches ou noires) :  

![Partition de musique](/assets/images/posts/music-scores/partition.png)

Les notes utilisent la notation anglo-saxonne : A (la) B (si) C (do) D (ré) E (mi) F (fa) et G (sol)

On vous fournit les images des partitions scannées en noir et blanc et encodées avec une forme simple mais efficace de RLE (Run-Length Encoding) : l'algorithme DWE (Doctor Who Encoding).

Dans le DWE, les pixels consécutifs de couleurs identiques sont encodés par une lettre (B pour les pixels noirs, W pour les pixels blancs) suivie d'un espace suivi du nombre de pixels de cette couleur.
L'encodage/décodage se fait de gauche à droite et de haut en bas.

C'est parti !

## Doctor Who Encoding

Pour pouvoir commencer à résoudre le puzzle, il faut reconstituer l'image à partir de l'input encodé de la manière suivante :  
Par exemple : W 5 B 20 W 16 pour 5 pixels blancs, suivis de 20 pixels noirs, suivis de 16 pixels blancs. On connaît les dimensions de l'image d'origine.

L'idée va donc être de créer une matrice composée de 0 (pixel noir) et de 1 (pixel blanc) de dimension w (largeur) x h (hauteur).  

Donc on découpe l'input en blocs de largeur w. Chaque bloc devient une ligne de notre matrice finale.
On a donc notre matrice de taille w x h constituée de 0 et de 1.

## Analyse de l'image

Nous allons partir de cette image pour expliquer les différentes étapes de résolution du puzzle.

![Partition de musique](/assets/images/posts/music-scores/example.png)

Pour connaître la hauteur et la couleur des notes nous allons devoir mettre en place plusieurs outils d'analyse de l'image.

Il va falloir connaître la hauteur des lignes et l'espacement entre les lignes.  

Pour cela, on commence par supprimer les colonnes blanches sur les bords droit et gauche de l'image, pour ne pas être parasité par ces colonnes-là.
Facile, comme les lignes noires vont d'un côté à l'autre sans discontinuer, il suffit de parcourir la matrice à la recherche de colonnes composées seulement de 1 et de les supprimer.

Nous obtenons donc après traitement cette image :

![Partition de musique](/assets/images/posts/music-scores/remove_white_column.png)

Grâce à cette nouvelle matrice on peut donc prendre la 1ère colonne et déterminer la hauteur des lignes noires et l'interligne de notre portée.  
Nous allons appeler cette colonne la colonne de "référence", elle va nous servir plusieurs fois pour la suite.

On peut aussi en déduire tous les intervalles de notes :  
On prend l'espace entre les lignes noires et on le divise par 2 (il y a deux hauteurs de note entre deux lignes).

Ensuite, nous allons parcourir notre matrice à la recherche des notes.  
Pour cela, nous allons parcourir notre matrice, colonne par colonne, de gauche à droite. Dès que nous détectons qu'une colonne est différente de la colonne de référence, c'est qu'il y a une note.  

Enfin ... c'est qu'il y a une note qui commence, donc on enregistre l'index de la 1ère colonne qui marque le début du bloc d'une note et on continue à balayer. Une fois qu'on retombe sur une colonne qui est égale à la colonne de référence, on enregistre la colonne précédente comme la fin du bloc qui contient la note.

Ainsi une fois qu'on a terminé de balayer notre matrice, on obtient une liste de blocs contenant chacun une note.

Exemple : [[10, 15], [20, 25], [25, 30]]  
La partition contient ici 3 notes : la 1ère commence à la colonne 10 et termine à la colonne 15 etc ...

Maintenant que nous avons les blocs contenant les notes nous devons déterminer leur hauteur dans la partition ce qui nous donnera la note.  
Donc, pour chaque bloc, nous allons balayer de bas en haut la matrice. Dès qu'on détecte qu'un pixel est différent de la colonne de référence, c'est qu'on tombe sur le contour haut d'une note. On l'enregistre et on passe à la colonne suivante.  
Ainsi, on va obtenir tous les pixels du bord haut de la note qu'on enregistre. Ce qui donne ceci plus ou moins. 

![Partition de musique](/assets/images/posts/music-scores/bord_haut_note.png)

Super, maintenant que nous avons ceci on a juste à évaluer où se trouve notre note.

Et pour la couleur ? On prend tous les pixels situés sur la ligne qui passe par le 1er pixel du bord haut de la note, si on trouve des pixels blancs, c'est une blanche, sinon c'est une noire !

Et voilà on a le nom de la note et sa couleur !

## Difficultés

J'ai malgré tout rencontré pas mal de difficultés.
Une seule m'a particulièrement embêté : ce sont les lignes supplémentaires sur les portées. 
Sur l'image suivante cela correspond au 1er DO qui n'est pas sur une ligne à proprement parlé, mais on voit la ligne dépasser un peu de chaque côté.  

![Partition de musique](/assets/images/posts/music-scores/exemple_do.png)

Cela pose souci lors de mon balayage horizontal.  
En effet, un autre exemple, à cause du trait qui déborde sous une autre note, je n'enregistre qu'une seule note et pas deux comme ici :

![Partition de musique](/assets/images/posts/music-scores/exemple_do_relou.png)

Une note qui commence de la 1ère colonne gauche de la 1ère note noire et qui finit à la dernière colonne droite de la 2ème note noire.
J'ai donc adapté mon code pour prendre en compte une notion de bruit. Je ne considère plus que l'enregistrement commence dès que la colonne est 100% égale de la référence mais plutôt 95%.

## Conclusion

Le puzzle semble complexe dans son ensemble, mais découpé petit bout par petit bout, et en avançant étape par étape il est finalement relativement simple à résoudre.
En tout cas je me suis beaucoup amusé à résoudre ce puzzle. Et je suis content d'avoir réussi à en venir à bout.

![Partition de musique](/assets/images/posts/music-scores/success.png)











