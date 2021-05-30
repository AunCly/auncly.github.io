---
layout: post
title:  "Créer un readme sur son profil github"
categories: [ Dev ]
image: assets/images/posts/github-readme/main.jpg
comments: false
excerpt: 
---

## Comment ça marche ?

Depuis, l'été 2020 Github permet à celle et ceux qui le souhaitent, d'agrémenter leur page public avec un readme.
Pour cela il suffit de créer un repo du même nom que votre pseudo sur github.  
Par exemple, mon pseudo Github est Auncly, j'ai donc créé un repo **Auncly/Auncly** .  
Si vous ne vous êtes pas trompé Github devrait vous afficher un petit message comme celui-ci.

![Message special](/assets/images/posts/github-readme/special-message.png)

Ensuite, il vous suffit de rédiger votre texte, vous pouvez y mettre des liens, images, etc. C'est vous qui choisissez. Vous devez simplement respecter la nomenclature [markdown](https://fr.wikipedia.org/wiki/Markdown). Comme ceci :  
Par exemple voici début de mon readme.md en syntaxe markdown.
```markdown
![Pyrenees](https://images.unsplash.com/photo-1554097092-bc5ad8df0f2d?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1953&q=80)
## En bref

Hello,
...
```

Vous pouvez aussi insérer des balises HTML qui sont aussi supportés.  
J'utilise **PhpStorm** comme éditeur de code pour mon travail et markdown est très bien supporté par cet IDE puisqu'il vous affiche une pré-visualisation en direct comme vous pouvez le voir :    

![Previsualisation en direct de PhpStorm](/assets/images/posts/github-readme/previsualisation.png)

Rien de compliquer ! Moi, j'ai fait simple pour mon readme, j'ai rédigé mon CV sur ma page, mais je sais que grâce aux [github actions](https://github.com/features/actions) il est possible de faire des choses beaucoup plus poussées, comme intégrer la liste de ses derniers articles publiés sur medium, ses dernières issues ou PR soumises, ou la liste des derniers repos dans lequel vous avez commit etc ... 
Si vous voulez vous faire une idée de ce que ça donne, voici le repo de [mon readme ici](https://github.com/AunCly/AunCly), qui met permet d'afficher sur mon [profil public](https://github.com/AunCly) le contenu de mon readme.  

Je vous mets [ici le lien vers la documentation officielle de github](https://docs.github.com/en/github/setting-up-and-managing-your-github-profile/managing-your-profile-readme) concernant cette feature.

Je vous dit à la prochaine !
