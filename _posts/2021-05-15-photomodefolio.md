---
layout: post
title:  "ModeFolio"
categories: [ Dev, Projet Perso ]
image: assets/images/posts/modefolio/main.jpg
comments: false
excerpt: Création d'un portfolio de mes images prises lors de mes sessions de jeu. 
---

## Concept

Depuis quelque temps de plus en plus de **mode photo** apparaissent dans les jeux vidéo. Ils permettent de stopper temporairement le jeu afin de permettre au joueur de capturer une image tout en lui offrant une multitude d'options qui vont lui permettre de modifier le rendu de son image.
Paramètres de luminosité, filtres, flou, certains éditeurs vont même jusqu'à proposer de changer la météo de la scène, changer les expressions du visage des personnages présents dans la scène, déplacer la caméra, ajouter du texte, etc.

![Mode photo Ghost Of Tsushima](/assets/images/posts/modefolio/death_stranding.jpeg)

Je souhaitais me créer un site web où je pouvais créer mes albums par jeu afin d'y ranger mes captures photos et vidéos, afin de pouvoir les partager avec tout le monde.  
Dommage pour moi il est compliqué de récupérer ses images depuis sa console et l'action de les récupérer puis de les uploader et les ranger sur mon éventuel site web m'ennuyais rien que d'y penser.

Maiiiiiiis voilà j'ai réfléchi et je me suis dit :   
Sur les playstations 4 et 5 il est possible de publier directement sur Twitter des photos et des portions de vidéos capturés en jeu et enregistrés sur la console.
J'utilise quotidiennement Twitter, je possède donc un compte et en plus lorsque l'on souhaite publier une photo sur twitter la playstation suggère automatiquement en Hashtag le nom du jeu.
Twitter possède son API ...  
Vous voyez où je veux en venir ?   

![u know what i mean](https://media.giphy.com/media/139O4f5FHk5dug/giphy.gif)

Est-ce qu'il n'y aurait pas un moyen d'utiliser l'API de twitter comme passerelle pour publier mes photos, puis de les récupérer pour les classer automatiquement dans un beau site web portfolio.

## Ou ça en est ?

Le projet est bien entamé, je récupère les images via l'API de Twitter, puis, je les classes par hashtag, je crée automatiquement un album par jeu.
Comme je suis un mec sympa, j'ai décidé de penser le projet pour tous, afin que n'importe qui puisse partager ses captures d'écrans sur un beau portfolio, automatiquement crée grâce à ses tweets.  

Côté plateforme, le back office est bien avancé, liste des albums, liste des images, modification des rattachements, suppression.
Finalement, le plus gros du projet réside dans le script d'importation des images. Pour l'instant il fonctionne via url mais, une fois terminé je le passerais en tâche programmé et en job.

![Administration des albums](/assets/images/posts/modefolio/modefolio-1.png)

## Technos

Les classiques, [Laravel](https://laravel.com/) / [Bootstrap](https://getbootstrap.com/docs/5.0/getting-started/introduction/), et [avantui](https://www.avantui.com/docs/getting-started.html) pour rajouter une légère couche de style rien de plus !  
Je suis parti sur les technos que je maitrise le plus pour aller le plus vite possible.

## La TODO

- S'inscrire directement avec twitter
- Basculer le script d'import en [CRON](https://laravel.com/docs/8.x/scheduling) ou en [JOB](https://laravel.com/docs/8.x/queues) pour que les utilisateurs puissent le lancer manuellement.
- Créer l'affichage front des albums
- Gestion du paramétrage du compte de l'utilisateur et de son album
- Récupérer les images de profil et de bannière depuis twitter
- Définir une image à la une pour les albums

Voilà ! C'est tout pour aujourd'hui, j'espère que le projet vous plait, si oui n'hésitez pas à me le dire par mail ou par twitter, la suite pour bientôt !  
