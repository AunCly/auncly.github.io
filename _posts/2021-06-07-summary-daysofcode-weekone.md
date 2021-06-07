---
layout: post
title:  "100DaysOfCode - semaine 1"
categories: [ Dev, 100DaysOfCode ]
image: assets/images/posts/summary-daysofcode-weekone/main.jpg
comments: false
excerpt: Bilan de la première semaine
---

## Organisation

Première semaine du challenge et j'ai réussi à preeeeeesque me tenir puisque j'ai quasiment fais tous les jours mon heure (et même plus en général) sauf vendredi soir où la fatigue m'a emporté, mais j'ai rattrapé mon retard puisque j'y ai passé 2h samedi !  

Pas facile de trouver le bon moment de la journée pour le challenge, le matin avant d'embaucher (mais cela fait se lever tôt, un peu trop tôt pour moi qui embauche à 8h), le midi pendant la pause (mais je n'ai pas vraiment l'impression de couper ma journée de travail) ou le soir à la maison.  

Pour le moment j'ai décidé de me caler ça le soir après le repas donc entre 20h et 21h environ. 
Sur la première semaine j'ai légèrement tendance à dépasser mon heure, je dirais que lissé sur la semaine j'ai passé environ 1h15 par jour.

## On se remet dans le bain

Doucement, j'ai ressorti mon livre de python3 qui prenait la poussière dans ma bibliothèque et j'ai entamé une lecture en diagonale. **[SPOILER ALERT]** En fait, j'ai déjà fait du python (il y a quelques années) lorsque je m'amusais sur codingame.  

Il s'agissait donc de se replonger dans la syntaxe du langage qui est assez différente de celui avec lequel je travaille toute la journée (Php).

Pas d'accolades, pas de parenthèses dans les conditions et les boucles, utilisation des ":", l'indentation, même encore au bout d'une semaine j'avoue que je peste encore contre moi de systématiquement mettre des parenthèses dans mes if, habitude quand tu nous tiens !
Mais ça va, j'ai réussi à bien me remettre dans le bain et j'ai de moins en moins de mal avec la syntaxe.

Après avoir revu l'essentiel des bases, conditions, boucle, fonctions et structure de données (liste et tuples), j'ai commencé à pratiquer un peu.
Et dès le 1er soir j'ai réalisé mon 1er "programme" le fameux *plus ou moins* dont voici le code : 

```python
import random

def print_hi(name):
    print(f'Hello, { name }')

def check_user_input(user_number):

    if user_number < 0 or user_number > 10:
        print("Le nombre doit être compris entre 1 et 10")
        return False

    return True

if __name__ == '__main__':

    print_hi("Aurélien")

    play_again = True

    while play_again:

        seeked_number = random.randrange(1, 10)
        number_is_seeked = False
        try_number = 1

        while not number_is_seeked:
            user_number = int(input("Trouvez le nombre compris entre 1 et 10 : "))

            if check_user_input(user_number):
                if user_number > seeked_number:
                    try_number += 1
                    print("C'est moins !")
                elif user_number == seeked_number:
                    print('Vous avez trouvé le nombre mystère.')
                    number_is_seeked = True
                else:
                    try_number += 1
                    print("C'est plus")

        print(f"Vous avez trouvé le nombre mystère en { try_number } coup(s)")

        user_response = False
        while user_response != 'Y' and user_response != 'N':
            user_response = input("Voulez vous rejouer ? Y/N ")

        if user_response == 'N':
            print("Merci d'avoir joué à bientôt")
            break
```

## Hackinscience

En réponse à mon deuxième tweet un utilisateur m'a conseillé d'essayer les challenges de [hackinscience](https://www.hackinscience.org/), je ne connaissais pas cette plateforme mais ça m'a intrigué je me suis donc inscrit le jour suivant pour voir ce qu'il en était.  

J'ai beaucoup accroché ! Les puzzles sont de difficultés croissantes et tout une partie est là pour apprendre les bases de python, parfait pour moi. J'ai passé le reste de ma semaine sur cette plateforme. Certains puzzles m'ont pris un peu plus de temps que d'autres (primes numbers par exemple) mais dans l'ensemble je trouve que j'avance bien.   

Les exercices sont souvent en français, mais certains énoncés sont en anglais. Les exercices sont top et la plateforme est super chouette, bref allez y faire un tour si vous voulez pratiquer un peu de python !

Voici un petit récapitulatif des puzzles que j'ai terminé : 
![Administration des albums](/assets/images/posts/summary-daysofcode-weekone/summary_hackinscience.png)

D'après la plateforme actuellement :  
Vous avez résolu 33 exercices, c'est 43% de tous les exercices.  
Vous avez 584 points, ce qui vous classe 258 sur 14494 participants.

![Pas mal non ?](https://media.giphy.com/media/62PP2yEIAZF6g/giphy.gif)

## Fin de semaine et objectifs

Septième jour, j'ai continué les puzzles sur hackinscience, le dernier sur lequel je me suis arrêté aujourd'hui demande de la conception de class en python, donc j'ai ré-ouvert mon bouquin pour un peu de lecture sur l'orienté objet en python.
Bilan de la semaine, je me suis bien mis dans le challenge et c'est agréable de jouer avec un autre langage de prog. Python est agréable à utiliser. La plateforme hackinscience me permet d'avoir un support sur lequel pratiquer tout en introduisant de plus en plus de concepts clés de python, c'est top.

Objectif : je vais essayer de ne pas me fixer d'objectif tant c'est difficile de savoir à quelle vitesse je vais apprendre et avancer. Je vais continuer les puzzles sur hackinscience pour sûr je veux grimper dans le classement !

C'est tout pour cette semaine, si cette aventure vous plait n'hésitez pas à me le dire sur [twitter](https://twitter.com/AunCly) ! 







