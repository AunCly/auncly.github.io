---
layout: post
title:  "100DaysOfCode - semaine 4"
categories: [ Dev, 100DaysOfCode ]
image: assets/images/posts/summary-daysofcode-weekfour/main.jpg
comments: false
excerpt: Et de un, un mois !
---

## Code Royale

Hello,

Comme prévu j'ai passé une bonne partie de ma semaine sur Code Royale de CodinGame, j'ai relativement bien avancé mais pas autant que je le souhaitais puisque je suis encore en ligue bronze. Le boss et mes adversaires sont coriaces !
Pour l'instant la stratégie est toute simple, je construis 2 ou 3 mines, puis une caserne pour produire des chevaliers et ensuite des tours pour me défendre.  
En ajoutant juste une fonctionnalité qui empêche ma reine d'aller sur un site qui se situe dans le rayon d'une tour, j'ai gagné pas mal de places.

J'ai testé pas mal de choses sans succès : 
   - Produire des archers lorsque la vie de ma reine est supérieure à celle de l'ennemie,
   - Gérer une notion d'agressivité selon le niveau de vie de ma reine,
   - Changer le nombre de bâtiments construits etc
  
Toutes ces fonctionnalités testées sont sur des branches à part sur github, ce qui me permet de ne garder que le code le plus performant sur ma branche "main". Ca me permet surtout de pouvoir garder le code de mes tests au cas où j'en aurais besoin plus tard.  
J'avoue que je ne sais plus trop vers quoi aller pour améliorer mon robot. Actuellement je suis 4ème de la ligue bronze.

![Code royale](/assets/images/posts/summary-daysofcode-weekfour/code_royale_classment.png)

Si près et pourtant si loin ...


## Puzzles

J'ai décidé de changer des challenges de bot pour reprendre les puzzles classiques de la plateforme.  

![Code royale](/assets/images/posts/summary-daysofcode-weekfour/puzzles_of_the_week.png)

Pour le moment je me concentre plutôt sur les puzzles "Facile" pour perfectionner mes connaissances en python, structures de données, algos, boucles etc ...  

J'ai résolu 3 puzzles cette semaine. Les 2 premiers sont classés "facile" : l'un consiste à dessiner le symbole de la triforce de Zelda selon une hauteur N donnée, l'autre consiste à trouver la plus longue suite de 1 dans une chaine binaire si l'on permute un, et un seul, 0 en 1.

Le 3ème est un puzzle de difficulté "Moyenne", mais ce n'est pas n'importe quel puzzle...  
Ce puzzle c'est un peu ma bête noire sur CodinGame depuis des années. Ce puzzle qui me fait baisser les bras à chaque fois que je me remets dedans.  

L'ennoncé est simple : 

> La citation "Des nains sur des épaules de géants" se réfère à l'importance pour tout homme de s'appuyer sur les travaux de ses prédécesseurs.  
>
> À la lecture des textes, on ne glane qu'une petite partie de cette dépendance : telle personne a influencé telle autre personne. On apprendra par la suite que cette seconde personne en a, à son tour, influencé une troisième, et ainsi de suite. C'est cette chaîne d'influence qui nous intéresse dans cet exercice, et plus précisément, il s'agit de trouver la longueur de la plus grande de ces chaînes.

J'ai décidé sans envie, aucune, de ré-essayer une nouvelle fois. Et ce qui devait arriver arriva !

![Code royale](/assets/images/posts/summary-daysofcode-weekfour/test_10.png)

rhaaaaa !  

Les tests exécutés lors de la soumission du code sont différents de ceux avec lesquels je peux essayer lors de la résolution normale du puzzle pour éviter les solutions "hard-codé".
Je modifie mon code et de nouveau les tests 7 et 8 ne passent plus, je peste, je fouille sur le forum, un des modérateurs a décidé de partager le jeu de test 8, celui qui finalement me manquait. Je dessine l'arbre sur une feuille et je me rends compte d'un cas que mon code ne gère pas.  

Quelques modifications de plus et enfin ça y est !

![Code royale](/assets/images/posts/summary-daysofcode-weekfour/dwarf_on_giants_shoulder.png)

Enfin quoi ! Je l'ai eu ! Quel bonheur. Plus jouissif que vaincre un boss sur dark souls ? Hum peut-être bien que oui !

![Victoire](https://media.giphy.com/media/mQG644PY8O7rG/giphy.gif)

Au final, il me restait du vieux code de ma dernière tentative il y a quelques mois, j'ai décidé de faire table rase, j'ai tout supprimé et en avant !
J'ai du passé environ 1h/1h30 dessus pour trouver la solution.
Au dela de la joie, je me rends compte de tout ce que j'ai appris lors de la résolution de ce puzzle :  
   - [Les listes d'adjacences](https://fr.wikipedia.org/wiki/Liste_d%27adjacence), par ex : { 1 : [2, 3], 2 : [4,5] }
   - [L'algorithme BFS](https://fr.wikipedia.org/wiki/Algorithme_de_parcours_en_largeur) (bread first search), algorithmes de parcours d'arbre en largeur
Merci les suggestions faites par Codingame lors de la présentation du puzzle.

Au final c'est bien 3 challenges et un niveau supplémentaire que j'ai validé cette semaine.  

Cap sur la mission "Niveau 20" !

![Code royale](/assets/images/posts/summary-daysofcode-weekfour/level_16.png)

On se revoit la semaine prochaine ! A plus !