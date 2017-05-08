---
layout: post
title:  Une refonte, pourquoi ?
date:   2017-04-12 09:41:00 +0100
categories: jekyll
---
Avant cette refonte, mon site était moche, difficilement administrable. J'en étais pas du tout satisfait et ai donc décidé de tout reprendre à zéro.

<!-- more -->

## Ce qu'il fallait améliorer

Mon ancien site était entièrement en HTML / CSS. J'utilisais un petit peu de PHP uniquement pour les includes et le formulaire de contact. J'avais donc un sérieux problème au niveau de l'administration du site. Si je voulais ajouter une page, je devais tout faire à la main, ce n'était vraiment pas l'idéal.

Au niveau de l'aspect visuel de mon site, c'était plutôt médiocre. En effet, je ne suis pas très doué dans cette discipline. Je n'étais pas satisfait du tout du rendu final.

Après avoir fait un état des lieux, j'ai décidé de faire une refonte complète afin d'intégrer de nouvelles fonctionnalités (comme ce blog, par exemple).

Avant de me lancer dans le développement, je suis passé par une phase de réflexion et de recherche pour savoir quelles technologies j'allais utiliser.

## Un générateur de sites statiques

Les fonctionnalités que je voulais ajouter sur mon site n'étaient pas très complexes :

- un blog
- la possibilité d'ajouter des nouvelles références facilement

Les **générateurs de sites statiques** sont parfaitement adaptés à ce genre de site, pour peu qu'on ne soit pas terrifiés par l'idée d'écrire en Markdown.

Ayant déjà utilisé [Pelican](pelican), j'ai d'abord étudié la possibilité de faire ce que je voulais avec. La gestion de contenu autre que les articles de blog n'est pas très simple.

J'ai donc été regarder du côté de [Jekyll](jekyll), qui est très utilisé, notamment pour sa facilité d'intégration aux GitHub Pages.

Outre une bonne communauté autour du projet, Jekyll intègre nativement la gestion de "collections". Ces collections permettent de définir des formes de contenus. Par exemple, si en plus d'un blog classique on souhaite ajouter une section avec des recettes de cuisine, il est très simple de définir une catégorie pour ces recettes. Ainsi les recettes ne seront pas postées au même endroit que les articles. De même, il est possible de créer un layout spécifique à cette collecction.

Exactement ce que je cherchais pour la gestion de mes références ! Adopté.

### Quelques plugins et services externes

le principal inconvénient que je voyais à l'utilisation d'un générateur de sites statiques est que ces derniers ne peuvent pas prendre nativement en charge la **gestion des commentaires**. En effet, ces derniers sont du contenu dynamique. De même, **un formulaire de contact** n'est pas envisageable.

C'est ici qu'intervient [Disqus](disqus). J'utilise ce service pour vous donner la possibilité de commenter mes articles.

[Formspree](formspree) permet d'ajouter un formulaire classique en HTML sur son site. Ensuite, lors de la soumission du formulaire, les données de ce dernier sont traitées par le service. Idéal pour ajouter un formulaire de contact sur mon site !

Les pages d'archives ne sont pas intégrées par défaut dans Jekyll, j'ai donc utilisé le plugin [jekyll-archives](jekyll-archives). Avec ce dernier j'ai créé la page gérant [les archives de mes catégories](/categories/).

### Design du site

Pour le design, j'ai changé ma charte graphique (qui était plutôt inexistante). Pour l'intégration, je suis parti du thème Minima (le thème par défaut de Jekyll) et l'ai entièrement adapté à mes besoins / envies.
Jekyll étant écrit en Ruby, le préprocesseur CSS Sass est directement intégré. Je l'utilisais déjà, génial!

Côté templates, Jekyll utilise la syntaxe Liquid, très simple à prendre en main et similaire à Jinja (utilisé par Pelican et Django).


[formspree]: https://formspree.io/
[disqus]: https://disqus.com/
[pelican]: http://docs.getpelican.com/
[jekyll]: https://talk.jekyllrb.com/
[jekyll-archives]: https://github.com/jekyll/jekyll-archives
