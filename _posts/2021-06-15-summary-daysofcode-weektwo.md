---
layout: post
title:  "100DaysOfCode - semaine 2"
categories: [ Dev, 100DaysOfCode ]
image: assets/images/posts/summary-daysofcode-weektwo/main.jpg
comments: false
excerpt: Deuxième semaine, le récap !
---

## Hackinscience

J'ai continué une partie de la deuxième semaine à pratiquer sur [hackinscience](https://www.hackinscience.org/), je trouve la plateforme très bien faite et les exercices sont de difficulté croissante et permettent chacun de découvrir de nouveaux concepts de python.

Bilan actuel sur hackinscience :  
Vous avez résolu 36 exercices, c'est 46% de tous les exercices.  
Vous avez 725 points, ce qui vous classe 216 sur 14749 participants.  

![Bilan hackinscience](/assets/images/posts/summary-daysofcode-weektwo/summary_hackinscience.png)

## CodinGame

Depuis jeudi dernier, j'ai quitté hackinscience et je suis je suis retourné sur [codingame](https://www.codingame.com/).  
Ce n'est pas une découverte et je connais déjà bien la plateforme, même si cela fait quelque temps que je n'y suis pas allé.

![Profil CodinGame](/assets/images/posts/summary-daysofcode-weektwo/profil_codingame.png)

J'avais déjà résolu quelques puzzles dans les sections facile et moyen en php et python.  
J'avais arrêté à ce moment-là car il n'y avait pas autant d'exercices qu'actuellement et que la difficulté des exercices qu'ils me restaient à faire était devenu trop élevée. Il me fallait plus de temps pour résoudre les puzzles que j'en avais à consacrer.

Malgré tout, la plateforme a continué à évoluer pendant ce temps, j'ai même vu qu'ils avaient implémenté un système de "Missions", top !

![Missions CodinGame](/assets/images/posts/summary-daysofcode-weektwo/missions_codingame.png)

## Mission : puzzle de la semaine
Dans mes missions disponibles sur CodinGame, il y avait "Résoudre le puzzle de la semaine", mission acceptée, on y va.  
Le puzzle en question : "Robot show", il s'agit de déterminer le nombre de tours qu'il faut afin qu'un nombre N de robots quittent une scène de largeur L. La règle, si deux robots se rencontrent, ils font demi-tour et repartent.  
L'énoncé est simple, me voilà parti. Évidemment ça ne c'est pas passé comme prévu.  
Si en effet l'énoncé est simple, je me retrouve vite bloqué, j'ai l'impression qu'il me manque une donnée cruciale sur l'orientation des robots au départ. Je réfléchis, je bloque, je réfléchis, je bloque. Je commence à me dire que je vais devoir simuler toutes les positions possibles, ce qui me parait un peu "complexe" pour un puzzle marqué comme "Facile".  

Je vais voir sur le forum dédié au puzzle, et un des premiers messages me fait tilt :
> CyberLemonade :  
> Just a friendly reminder to anyone who is trying brute force that this puzzle was labelled easy for a reason. 

Il doit forcément y avoir une solution simple mais non-évidente. Après plusieurs schémas et simulation sur papier, je commence à me faire une idée et à comprendre la mécanique.
Après quelques recherches de plus, ça y est je mets le doigt sur la solution : 5 lignes.
Je ne donnerais pas la réponse ici, pour ne pas spoiler la solution.

Tous les tests sont au vert, je suis super content et ma mission est désormais accomplie. J'aurais au final passé ~1h30 sur ce puzzle. 

![Mission Succeeded](/assets/images/posts/summary-daysofcode-weektwo/mission_succeeded.png)

## Ghost in the shell

J'ai aussi passé pas mal de temps sur un challenge d'IA : **Ghost in the shell**
J'avais déjà essayé à l'époque sur le challenge coder strike back, mais je n'arrivais pas à progresser et je m'étais vite découragé.
J'ai donc ré-essayé avec un autre des exercices conseillés pour débuter : Ghost in the shell.

Comment ça marche ? Pour un enoncé donné vous devez écrire votre propre bot afin de battre votre adversaire.
Le classement est découpé en ligue Bois 3, Bois 2, Bois 1, Bronze, Argent, Or et Légende.


**Ghost in the shell** : Le principe ? Vous devez détruire l'armée de robots de votre ennemi. Sur une map généré aléatoirement sont disposés N usines qui produisent des robots. Vous démarrez avec un certain nombre de robots disposés dans une usine. Votre adversaire démarre avec le même nombre de robot dans une usine lui aussi.  

Et voila ! A vous d'écrire le code qui vous permettra de vaincre vos adversaires.
J'ai commencé avec une stratégie plutôt basique qui a été plutôt efficace pour m'emmener en ligue bronze. Mais elle avait ses limites et je n'arriverais pas à changer de ligue en gardant cette stratégie.
Sur la fin de la semaine j'ai ré-écrit le code de mon bot pour le convertir en POO (programmation orientée objet) afin de mieux m'organiser et que le code soit plus lisible et maintenable. J'ai mis en place un repo github privé aussi avec le code de mon bot afin de pouvoir profiter du système de branches pour faire des tests sur des stratégies différentes.
Je me suis aussi rendu compte que j'avais encore beaucoup de lacunes sur les bases de python, je vais donc essayer de passer plus de temps à lire mon bouquin sur python la semaine prochaine afin de mieux me familiariser avec les concepts et la syntaxe de python sur les structures de données et la POO.

## Temps passé

Au final j'ai super accroché au combat de bot et j'avoue que j'ai passé bien plus d'une heure par jour cette semaine. Environ 2h par jour, je dirais.  
Une fois que je suis lancé, c'est super dur de s'arrêter !

C'est tout pour cette semaine ! Merci de suivre cette aventure avec moi ! A la semaine prochaine !