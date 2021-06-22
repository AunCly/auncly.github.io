---
layout: post
title:  "100DaysOfCode - semaine 3"
categories: [ Dev, 100DaysOfCode ]
image: assets/images/posts/summary-daysofcode-weekthree/main.jpg
comments: false
excerpt: Bilan de la troisième semaine.
---

## Ghost In The Cell

J'ai passé quasiment toute ma semaine sur ce challenge. Mon bot a bien progressé et je suis passé de la ligue Bois 3 à la ligue Bois 1 assez facilement avec quelques lignes de python.
Une fois la ligue Bois 1 passée avec quelques modifications, me voilà arrivé en ligue bronze. Confiant j'attaque cette nouvelle ligue, mais tout ne se passe pas comme prévu.  

Il faut savoir que de nouvelles règles s'ajoutent à chaque nouvelle ligue.  

Nouvelles règles :  
   - En ligue Bois 2, la limite d'une seule instruction par tour est enlevé on peut donc envoyer autant d'instructions qu'on veut dans le même tour,
   - En ligue Bois 1, les bombes font leurs apparitions, elles tuent la moitié des robots disponibles dans l'usine au moment où elles arrivent et empêche la production de robots pendant 5 tours,
   - En ligue Bronze, on peut maintenant augmenter la production des usines jusqu'à un maximum de 3 robots par usine par tour.

![Ghost in the cell](/assets/images/posts/summary-daysofcode-weekthree/ghost_in_the_cell.png)

Le boss de la ligue bronze est beaucoup plus coriace et les bots de mes adversaires de ligue aussi. À chaque fois que j'essaye d'ajouter de nouvelles options à mon code, j'arrive à grapiller quelques places mais sans plus !
J'ai ajouté beaucoup de possibilités :
   - la détection et l'évacuation des usines lorsqu'une bombe est sur le point d'arriver,
   - une règle d'augmentation de la production lorsque mon nombre de robots est supérieur à celui de l'adversaire,
   - une règle pour l'envoi de bombes lorsque la production de l'ennemi est supérieure à la mienne.  

J'ai changé ma manière d'attaquer mon adversaire en essayant de gérer les usines individuellement ou en les synchronisant. J'ai fait beaucoup de tests de stratégies sans grand succès.  
Au mieux je suis arrivé à la 184ème place de la ligue bronze ce qui est loin d'être suffisant puisqu'il faut être premier pour changer de ligue.  

## Code Royale

![Code royale](/assets/images/posts/summary-daysofcode-weekthree/code_royale.png)

Sentant que je n'arriverais pas à faire plus de progrès sur ce challenge, j'ai décidé de prendre un peu de recul et d'en essayer un autre pour changer d'air.  
Je voulais essayer un autre type pour voir d'autres typologies de challenge de bot.
J'ai donc choisis un challenge radicalement différent puisqu'il s'agit aussi d'un challenge de gestion de ressources.

![Stupide boy](https://media.giphy.com/media/7Jq6ufAgpblcm0Ih2z/giphy.gif)

Pour ceux qui connaissent le jeu clash royale le challenge s'y apparente bien que les règles sont super simplifiées par rapport au jeu (surtout sur le nombre d'unités en fait).
L'idée est de tuer la reine adverse en essayant de construire des bâtiments qui vont nous permettre de créer des unités qui vont attaquer la reine ennemie.  

Tout l'intérêt réside dans l'occupation de la map et dans la gestion de ses unités.
J'ai traversé les ligues bois plutôt facilement je dois dire, cette fois-ci j'ai organisé dès le départ mon code en orienté objet.
Au moment où j'écris ces lignes je trône à la 916/1322ème place de la ligue bronze !

J'ai d'ailleurs découvert que l'on pouvait supprimer l'adversaire de base proposé par la plateforme en y mettant l'IA d'une autre personne de sa ligue, pour pouvoir mieux analyser sa défaite ou sa victoire !  

## Encore et encore
Je dois avouer que je prends un plaisir fou sur ces challenges d'IA, moi qui ai un fort esprit de compétition c'est tout ce qu'il me fallait, des ligues, un classement de ligue, le rêve.  
Lorsque que quelque chose me plait j'ai tendance à ne faire et ne penser qu'à ça. C'est exactement ce qui m'arrive en ce moment avec ces challenges de bot !  
Heureusement j'ai fait l'acquisition de nouveaux sets de légo pour me détendre à côté mais ça c'est une autre histoire ... dans un prochain article !

On se revoit la semaine prochaine, en espérant avoir pu avancer dans ma ligue ! A plus !