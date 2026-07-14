---
title: "Mise en ligne d’un blog statique avec Jekyll et GitHub Pages"
date: 2025-11-03
categories: [Blog]
tags: [Blog]
---

# Jekyll : un générateur de site statique

Jekyll est un générateur de site statique écrit en Ruby, qui permet de transformer des fichiers Markdown ou HTML en un site web complet (HTML, CSS, JS), sans base de données ni backend dynamique.

En tant que développeurs, nous passons une bonne partie de notre temps à documenter nos travaux dans nos différents dépôts de code, souvent en utilisant la syntaxe Markdown. Il est donc intéressant de capitaliser sur cette compétence pour créer un blog technique ou un site personnel avec Jekyll.

Ce qui rend la démarche encore plus intéressante, c’est l’existence de thèmes Jekyll prêts à l’emploi, comme le populaire Chirpy. Ce thème offre une présentation moderne, élégante et optimisée pour les blogs techniques. Ainsi, tout ce dont vous avez besoin est un compte GitHub, et vous pouvez lancer votre propre blog professionnel en quelques minutes seulement.

# Héberger son site avec GitHub Pages

Avec GitHub Pages, tu peux héberger gratuitement des sites web statiques directement à partir d’un dépôt GitHub. C’est une solution très intéressante pour les développeurs qui souhaitent créer un blog afin de partager leurs connaissances. En plus, ton site est hébergé dans un dépôt versionné, ce qui te permet de suivre facilement l’historique des modifications, de collaborer avec d’autres contributeurs et de déployer automatiquement les mises à jour dès que tu pousses du code sur ton dépôt.

# Objectif de cet article

Cet article explique, étape par étape, comment mettre en ligne un blog en utilisant Jekyll et GitHub Pages. Tu y découvriras comment configurer ton environnement, personnaliser ton site et le déployer gratuitement sur GitHub. Une solution simple et efficace pour partager tes connaissances techniques ou tenir un journal de veille en ligne.

Il ne vous reste plus qu’à suivre les étapes ci-dessous pour créer et publier votre blog en ligne.

Prerequis
- Avoir un compte github. 
- Avoir Ruby installer sur sont poste local

## Créez le dépôt GitHub de votre blog en utilisant le modèle officiel fourni par Chirpy

Se rendre sur se repo du theme chirpy [theme chirpy](https://github.com/cotes2020/chirpy-starter) et creer un repo dans votre compte a partir de ce dernier `Use this template -> Create a new repository`

![Texte alternatif](/assets/images/2025-11-03-mise-en-ligne-d-un-blog-statique-avec-jekyll-et-github-pages/4.png )

Choisissez le nom de votre dépôt. Celui-ci doit respecter la syntaxe suivante : `votre_username_github.github.io`

NB: Pour publier votre blog via ce dépôt avec GitHub Pages, celui-ci doit être public.

![Texte alternatif](/assets/images/2025-11-03-mise-en-ligne-d-un-blog-statique-avec-jekyll-et-github-pages/repo-name.png )

## Clone votre repo en local et vous rassurer qu'il demarre

```bash
$ git clone 
$ cd 
$ bundle exec jekyll serve
```

Le site est accessible à l’adresse suivante : [http://localhost:4000](http://localhost:4000)

Passons en revue les fichier et dossier utilise. Nous n'avons pas pour objectif de modifier le code source. Donc nous allons nous focaliser sur les fichier pour personnaliser le site a notre image.

`📁 _posts` 

 Ce dossier contient les articles de ton blog. Chaque fichier correspond à un article, généralement nommé selon le format `YYYY-MM-DD-nom-de-l-article.md`.
Les fichiers placés ici seront automatiquement affichés dans la liste des publications sur ton site.

`📁 _tabs`

Ce dossier contient les pages qui servent de menu principal à ton site (ex. : À propos, Contact, Catégories…).
Si tu ajoutes un nouveau fichier dans ce dossier, un nouveau lien de menu sera automatiquement créé.

`📁 _layouts`

Ce dossier contient les gabarits de pages (layouts) utilisés pour définir la structure des différentes pages du site.
Par exemple, tu peux avoir un layout pour la page d’accueil, un autre pour les articles, etc.

`📁 _includes`

Ce dossier regroupe les fragments de code réutilisables, comme l’en-tête, le pied de page ou la barre latérale.
Tu peux les insérer dans tes layouts à l’aide de la balise {% include nom_du_fichier.html %}.

`📁 _data`

Ce dossier contient des fichiers de données (souvent en YAML, JSON ou CSV) utilisés pour alimenter dynamiquement ton site.
Par exemple, tu peux y stocker la liste de tes projets, de tes réseaux sociaux ou de tes partenaires.

`📁 assets`

Ce dossier regroupe les ressources statiques de ton site, comme les images, les fichiers CSS, JavaScript ou les polices.

`📁 _config.yml`

Il s’agit du fichier de configuration principale de ton site Jekyll.
Tu y définis les paramètres globaux : le titre du site, la description, les liens de navigation, le thème utilisé, etc.
Toute modification dans ce fichier impacte le comportement global du site. 

<!-- `_config.yml` : Ce fichier contient les information de votre votre profil tel: _nom_, _avatar_, _liens sociaux_ etc...
`_loyout` : Contien les page de base differente cateforie de page de notre site. 
`_tabs` : Conttien les page faisont office de menu de notre site. Si vous ajouter un fichier dans ce dossier, vous verrez un nouvaun lien de menu se creer  


La methode que je vais vous montrer vous permettra ne de ien modificie sur le code source, vous n'aurez qu' renseigner votre profil et ajouter des article
2. Petit tour des fichier un dossier important.
    - Fichier `_config.yml`
    - Dossier `_layout`
    - Dossier  `tabs`
    - Dossier `_post`
    - Dossier `_data`
    - Dossier `assets`

Par defaut votre blog a 5 menu,









![Texte alternatif](/assets/images/2025-11-03-mise-en-ligne-d-un-blog-statique-avec-jekyll-et-github-pages/1.png )


https://github.com/cotes2020/chirpy-starter -->




