---
layout: post
title:  "100DaysOfCode - semaine 5 et 6"
categories: [ Dev, 100DaysOfCode ]
image: assets/images/posts/summary-daysofcode-week-five-and-six/main.jpg
comments: false
excerpt: Récap des semaines 5 et 6 de mon 100DaysOfCode
---

## CodinGame, encore et toujours

Hello,  
comme les semaines précédentes, j'ai passé tout mon temps sur codingame. Je suis vraiment devenu accro à la plateforme. Je trouve qu'elle me permet d'apprendre régulièrement de nouveaux concepts et la variété de puzzles me permet de pouvoir alterner entre programmation de bot, puzzles, clash of code et optimisation.  

Le système de succès et de missions me plaît beaucoup. J'ai passé une bonne partie de ma vie plongé dans les jeux en ligne alors forcément de l'xp, des quêtes et des trophées, c'est parfait.  
Je ne m'ennuie jamais.  
Le fait d'avoir un classement en plus permet de pouvoir voir ma courbe de progression sur la plateforme même si cela n'est pas forcément représentatif parfois, mais cela permet d'avoir un sentiment de progression (enfin pour moi en tout cas).

## Optimisation
J'ai commencé à m'initier aux puzzles d'optimisation de la plateforme avec Code Vs Zombie. Comme énoncé dans la consigne les puzzles d'optimisation sont simple à résoudre mais c'est l'optimisation qui va compter.
Par exemple sur code vs zombie, le but est simple, sauver les humains en tuant les zombies dans la zone. Les zombies se déplacent toujours vers l'humain le plus proche d'eux.  
Notre code doit donc faire déplacer un humain armé d'un fusil. Dès qu'un zombie est proche de lui d'une certaine distance, il fait feu et tue le zombie.  

Pour que les tests du puzzle soient validés il faut sauver au moins un humain. Mais (et c'est là que toute la différence va se faire sur le score) plus on sauve d'humain pour le score augmente, plus on tue de zombie à la chaine pour le score est multiplié !  

Ma première solution naïve a été de calculer le point qui est au milieu des humains dans la zone. Ce qui marche dans certains cas mais pas tous (par exemple lorsque les humains sont trop espacés sur la map).

La solution suivante a été de me ruer sur l'humain le plus proche de moi en début de partie et de le défendre (je pensais que cela me permettrait de valider au moins chacun des tests). Mais dans certains cas l'humain le plus proche de moi en début de partie est déjà condamné car un zombie est plus proche de lui que moi.

![Code VS Zombie](/assets/images/posts/summary-daysofcode-week-five-and-six/code-vs-zombies.png)

Donc j'ai décidé de prendre en compte la chance de survie de l'humain. Je prévois qui sera le plus vite sur l'humain de moi ou du zombie et j'avise. 
A partir de la j'ai réussi à valider 100% des tests. En effet, j'ai trouvé une solution qui me permet de sauver au moins un humain à chaque fois !

Mais ce n'était pas suffisant pour valider ma mission qui était d'obtenir un score d'au moins 40 000 points. A ce stade la je suis aux environs de 31 000 points, ce qui n'est pas trop mal mais un peu juste.

Au final j'ai atteint les 50 000 points avec la solution suivante (qui ressemble beaucoup à la solution précédente). Mission accomplie donc !  

![Mission Code VS Zombie](/assets/images/posts/summary-daysofcode-week-five-and-six/optimization-quest.png)

Au classement je suis ~2000/10 000, il me reste encore une bonne marge d'amélioration pour ce puzzle. J'y retournerai surement plus tard. J'ai trouvé ce puzzle et son concept super sympa.

## Treize à la douzaine

Durant ces deux semaines j'ai résolu encore quelques puzzles de plus pour un total de treize puzzles terminés. 
La majorité des puzzles est parmi les faciles 10/13 et 3 moyens. Ces puzzles me permettent, je trouve, d'être de plus en plus à l'aise avec python, notamment sur les structures de données de base et sur certaines astuces.  

![Puzzles](/assets/images/posts/summary-daysofcode-week-five-and-six/puzzles.png)

## Ghost in the cell Come-Back

![Ghost in the cell](/assets/images/posts/summary-daysofcode-week-five-and-six/ghost-in-the-cell.png)

J'ai décidé de me relancer dans la programmation de bot sur Ghost in the cell que j'avais laissé de côté en semaine 3. Lors de ma reprise j'étais classé ~200/2400ème en ligue bronze.
J'ai commencé par faire du ménage. Avec code royale, j'ai découvert quelques concepts d'orienté objet que je n'avais pas mis en place à ma première tentative.

Une fois le nettoyage fait, j'ai refait quelques tests qui m'ont permis de gagner quelques place et je suis arrivé ~50ème de la ligue bronze. A partir de là, je me suis remis à stagner.
J'ai été lire quelques PostMortem de joueurs. Les PostMortem sont des résumés de stratégie et de manière de faire des meilleurs joueurs durant la période où le puzzle était en contest. Et cette lecture m'as confirmé ce que je savais déjà mais que je me refusais de voir. Il allait me falloir implémenter un algorithme de chemin le plus court pour optimiser le trajet de mes robots lors de mes attaques.

![Here we go](https://media.giphy.com/media/ncbdoCpKerEbK/giphy.gif)

J'ai sorti mon livre d'algorithmes pour les nuls et commencé à lire un peu la section des algos de chemin le plus court. Il faut savoir que tout ces concepts sont nouveaux pour moi. Malgré le fait que je bosse comme développeur depuis plusieurs années, je n'utilise jamais ce genre d'algo lors de la programmation de site web.  
Je ne suis pas du tout à l'aise avec toutes ces logiques qui sont plus proche des mathématiques que de la programmation.

La plupart des choses que j'ai pu lire par-ci par-la dans mon bouquin et sur le net m'ont orienté vers un l'algorithme de Dijkstra pour calculer le chemin le plus court dans mon graphe.  
J'ai regardé quelques vidéos détaillant le fonctionnement de l'algo.
Quelques heures plus tard, toujours sans résultat, je demande sur le tchat de Codingame si je suis parti dans la bonne direction avant de m'acharner plus sur l'implémentation de cet algo.  
Un membre me conseille plutôt de regarder l'algorithme de Floyd Warshall étant donné que l'emplacement des factories est déterminé une seule fois en début de partie.  

Je retourne me documenter. Je comprends plus facilement cet algo et j'arrive à le mettre en place relativement facilement.
Maintenant j'ai un algo qui me permet de trouver l'usine intermédiaire la plus proche de deux autres usines dans la carte.
J'ajoute cet algo à mon programme pour Ghost in the cell, j'affine deux trois petites choses et les yeux fermés, je lance mon code dans l'arène.
Au bout de quelques minutes, je vois que je suis premier et même au dessus du boss, parfait, je passe donc en ligue argent !  

Tout juste arrivé en ligue argent je relance mon code dans l'arène et quelques minutes plus tard je me retrouve 180ème de la ligue argent !

![Classement ghost in the cell](/assets/images/posts/summary-daysofcode-week-five-and-six/classement-ghost-in-the-cell.png)

La route est encore longue mais je suis super content d'avoir réussi à mettre en place mon algo de chemin le plus court. Et cela même si je n'ai pas réussi à implémenter l'algorithme de Dijkstra. Mais j'ai compris le principe et je pense que la prochaine fois, je saurais à le mettre en place si besoin.  
Je suis fier d'apprendre, comprendre et mettre en place de nouvelles mécaniques dans ce genre. Car comme je le disais, je ne suis pas du tout familier de ces concepts. Ce sont donc de petites victoires pour moi.

That's all ! See you soon !