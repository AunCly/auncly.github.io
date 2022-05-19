---
layout: post
title:  "CodinGame - Spring Challenge 2022"
categories: [ Dev ]
image: assets/images/posts/spring-challenge-2022/main.jpg
comments: false
excerpt: Récap de ma participation au CodinGame Spring Challenge 2022
---

## Principe
Le challenge est un combat de bot (robots), autour d'un sujet donné, le développeur doit programmer son bot afin de répondre au sujet.
Une fois le bot programmé, on le soumet et il affronte les bots des autres joueurs. Ce qui donne le score du bot et donc son classement.

## Règles du jeu

Ca y est le jour tant attendu est arrivé. Le contest débute à 16h tout pile ! Voici l'énnoncé :

Protégez votre base de la vague de monstres plus longtemps que votre adversaire.
Les deux joueurs contrôlent une équipe de 3 héros. Les équipes commencent aux coins opposés de la carte, près de leur base.  
Tout au long du jeu, des monstres apparaîtront régulièrement sur les bords de la carte. Si un monstre atteint votre base, il infligera un point de dégât. Si votre base subit trop de dégâts, vous perdez.
Heureusement, vos héros peuvent tuer les monstres.

A chaque tour de jeux chacun de nos héros peuvent faire 5 actions :
MOVE x y : Se déplacer vers les coordonnées (x,y)
WAIT : Attendre
SPELL WIND x y : Lancer un sort de vent qui repousse de 2200 unités les entités autour de lui (monstres, héros et héros adverse) dans la direction (x,y)
SPELL CONTROL entity_id x y : Contrôler pendant 1 tour l'entité ayant l'id entity_id et l'envoie dans la direction (x,y)
SPELL SHIELD entity_id : Créer un bouclier autour de l'entité ayant l'id entity_id pendant 12 tours ce qui lui empêche de subir des attaques de sort pendant ce temps.

Voici une image de la carte :
![Map spring challenge 2022](/assets/images/posts/spring-challenge-2022/map.png)
La carte fait 17630 x 9000 unités.

Ma base est en haut à gauche dans la partie verte claire et mes héros sont bleus.
La base de l'adversaire est en bas à droite et ses héros sont rouges.

Détails importants :
- Du brouillard rend impossible de connaître la position de tous les monstres et des héros rivaux. Vous devez les avoir à moins de 2200 unités d'un de vos héros ou 6000 de votre base POUR ???.
- Chaque base peut subir un maximum de 3 points de dégâts avant d'être détruite.
- Les héros attaquent automatiquement tous les monstres situés à 800 unités d'eux.
- Pour lancer un sort, les héros ont besoin de mana. Ils peuvent gagner en attaquant les monstres (1 point de mana par point de dégât infligé à un monstre).
- Si aucune des deux bases n'a été détruite, le jeu s'arrête au bout de 220 tours, et c'est le joueur ayant gagné le plus de points de mana *en dehors de sa base*(en dehors de la partie verte claire donc) qui gagne.
- Au fur et a mesure des tours les monstres ont de plus en plus de points de vie.

![Map spring challenge 2022](/assets/images/posts/spring-challenge-2022/map-overlay.png)
Voici la map en mode débug : 
- Le petit arc de cercle gris en haut à gauche indique la zone critique de ma base, si un monstre l'atteint, je perds 1 point de vie.
- L'arc de cercle bleu représente la zone d'influence de ma base
- Mes héros sont toujours en bleu.
- L'arc de cercle rouge représente la zone d'influence de la base de l'adversaire
- Le petit arc de cercle gris en bas à droite indique la zone critique de la base de l'adversaire, si un monstre l'atteint, il perd 1 point de vie.
- La zone noire représente le brouillard de guerre, je ne peux rien voir de ce qui se passe dans cette zone si je n'y vais pas.

## Principe des ligues

Le classement est décomposé en plusieurs ligues (comme pour le foot) : Ligue bois 2, Ligue Bois 1, Ligue Bronze, Ligue Argent, Ligue Or et Ligue Légende.
Pour changer de ligue, il faut affronter les bots des autres développeurs pour monter dans le classement.  

Une fois en haut de la ligue, il faut battre le boss de la ligue. Si notre classement est meilleur que celui du boss, on grimpe dans la ligue supérieure.
On ne peut que monter de ligue, jamais descendre (pas comme le foot donc :p ).

Il faut donc arriver à coder un bot qui soit à la fois performant contre les autres développeurs, mais aussi contre le boss, c'est surement un détail pour vous, mais ça a eu son importance sur la fin du challenge.

## Ligue Bois 2, bois 1 et Bronze

J'ai commencé le contest en Python, mais j'ai ré-écrit le code en PHP ; langage que je maitrise bien plus.

C'est la 1ère fois que je participe à un contest de ce genre donc je suis parti sur une idée simple pour essayer de ne pas m'éparpiller.
Pour les premières ligues, je me suis occupé d'attaquer les monstres qui s'approchent de ma base avec mes 3 héros. Chaque héro se dirige vers le monstre le plus proche de ma base.  

S'il n'y a pas de monstre les héros se déploient en arc de cercle autour de ma base.  
Ils utilisent le sort de vent lorsque les monstres sont très proche de ma base pour les repousser et me laisser le temps de les tuer. Je n'ai pas eu à faire plus de chose pour arriver en ligue argent.

## Ligue Argent
Arrivé en ligue argent, j'ai commencé par changer de stratégie. J'ai décidé de passer en mode un attaquant et deux défenseurs :
- Les défenseurs défendent ma base contre les monstres et l'attaquant attaque la base adverse en poussant, à l'aide du vent, les monstres dans la base de l'adversaire.
- Les défenseurs se dirigent vers les deux monstres les plus proches de la base, et chaque héro va vers le monstre le plus proche de lui.
- Pour l'attaquant, j'ai dû me replonger dans la trigonométrie afin de positionner mon héro et le faire osciller sur l'arc de cercle de la base ennemie.

## Ligue Or

C'est vraiment en ligue Or que tout c'est compliqué pour moi. La ligue est dense (~2000 personnes) et les développeurs ont tous des stratégies très différentes :
- Triple défenseurs
- Double défenseurs + un attaquant (la majeure partie de la ligue Or)
- Triple attaquants

C'est très difficile d'avoir un bot performant contre toutes ses stratégies.  
De plus les temps de soumission de notre code sont très longs. Cela peut prendre plusieurs heures parfois pour savoir si une modification est efficace ou non. Je ne peux donc pas tester beaucoup de choses.
Après avoir corrigé un bug, je me retrouve parfois avec un classement moins bon que le précédent : c'est très frustrant.

J'ai modifié le code de mon héro attaquant :
- il utilise le sort vent pour pousser un monstre dans la base adverse,
- puis il met un bouclier sur ce monstre afin que les héros adverses ne puissent pas le repousser,
- si un héro adverse est trop proche du monstre, mon héro lui lance un sort de contrôle pour l'éloigner et laisser le temps au monstre d'arriver sur la base adverse.

Au final, je trouve que ma stratégie marche assez mal et je modifie le code de mes attaquants sur la fin du challenge pour utiliser le vent de manière plus efficace. 
Je simule 36 positions (360/10) de direction du vent ce qui me permet de :
- Savoir si le montre peux être poussé directement sur la base adverse pour lui faire des dégâts
- Savoir si le montre va se retrouver dans le rayon d'un héro adverse
- Savoir si le monstre va heurter les bords de la map (ce qu'il faut éviter, car le monstre arrête sont déplacement de vent à cet endroit)
Aussi dès que mon attaquant fait un sort de vent je me dirige dan sla position d'arrivé de ce monstre pour éventuellement le repousser et ainsi de suite.

J'ai aussi modifié le code de mes défenseurs afin qu'ils utilisent moins de mana pour en laisser un peu plus à mon attaquant.
Par exemple, je simule les coordonées de plusieurs positions de vent afin que le monstre n'arrive pas dans le même cercle qu'un ennemi (qui risque de le repousser de nouveau dans ma base).
Malgré tout, impossible de battre le boss de la ligue Or.

Après plusieurs analyses des matchs que je perds, j'ai essayé le dernier dimanche après-midi de changer complètement de stratégie et d'utiliser 3 attaquants afin de pouvoir utiliser 3 vents sur les monstres à proximité de la base ennemie, (3 vents = 3 x 2200 unités = 6600 unités de déplacement d'un coup) mais en vain.
Avec la fatigue de la semaine, je n'ai pas réussi à coder cette idée correctement. J'ai décidé d'arrêter le contest le dimanche vers 16h environ et de prendre un peu de repos bien mérité.

Voici un replay d'un des match que j'ai gagné par exemple : [https://www.codingame.com/replay/630957513](https://www.codingame.com/replay/630957513)

## Classement Final et bilan

![Map spring challenge 2022](/assets/images/posts/spring-challenge-2022/classement.png)

Je termine finalement 480ème du classement général, 90ème place de la ligue Or. Je suis content de mon classement pour un 1er contest mais aussi très déçu.  
J'ai un énorme esprit de compétition et je me suis vraiment battu pour essayer d'atteindre la ligue légende sans réussir à y arriver.
Si je dois analyser ce qui m'a surement fait du tort pendant le contest, je dirais que :
- Je me suis trop éparpillé dans trop de solutions (parfois je ne testais même pas le résultat d'une idée et je commençais à en coder une autre),
- Je ne suis pas assez bon en maths et je pense qu'avec une meilleure connaissance de la trigonométrie et des vecteurs j'aurais pu faire plus de chose. L'interception des monstres par exemple plutôt que de les suivre ou me placer à l'intersection des plusieurs cercles pour optimiser les dégats sur plusieurs monstres,
- Je n'ai pas assez analysé les défaites de mon bot,
- Je me suis fixé un objectif trop élevé pour un 1er contest,
- Dormir plus, même si je le savais déjà. Coder fatigué n'est pas une riche idée.!
  Malgré tout j'ai trouvé le contest hyper cool, j'ai réussi à rester motivé pendant toute la durée du contest (11 jours). J'ai pu lire sur le forum toutes les idées des autres joueurs et je suis impréssionné par leurs stratégies et leur efficacité à les programmer.
  Maintenant j'ai hâte au prochain challenge et en attendant je peux essayer de battre ce fichu boss de ligue Or puisque le jeu a été ouvert en jeu d'entrainement sur la plateforme ! 














