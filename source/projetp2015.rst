=================================
Projet -- Printemps 2015
=================================

Blog
====

Objectif
++++++++

L'objectif de votre projet est de produire, en binôme, un blog dynamique.
Votre projet reprendra et adaptera les sources de votre maquette de blog du `projet d'introduction au Web`__. 

__ http://liris.cnrs.fr/~mgueriau/wiki/doku.php?id=fr:teaching:iut

Cahier des charges
++++++++++++++++++

Votre blog utilisera les technologies PHP/MySQL, en plus des éléments déjà écrits en HTML/CSS (toujours pas de Javascript).
La notation ne portera que sur les nouveaux éléments dynamiques (base de données, scripts PHP).
Les deux projets étant évalués de manière indépendante, les ajouts HTML/CSS ne seront pas évalués.
Vous devez implémenter toutes les fonctionalités qui suivent et choisir l'une parmi les 4 proposées dans le dernier paragraphe.


Données à gérer (liste minimale) dans une base de données :

* articles (titre, résumé, date d'ajout, rédacteur, image, contenu, ...)
* commentaires (rédacteur, date d'ajout, contenu, ...)
* utilisateurs (identifiant, mot de passe, type de compte (user/webmaster), date de création du compte ...)

.. nextslide::

La liste des fonctionnalités attendues par page est la suivante :

* page accueil : 

  - résumé de l'article le plus récent du blog (titre, résumé, image);
  - commentaire le plus récent de l'article le plus récent (le cas échéant ; identifiant, date d'ajout et contenu du commentaire).
  
* page de résultat de recherche :

  - tableau de titres et dates d'ajout d'articles correspondants aux mots clés entrés;
  - affichage d'une copie de la zone de recherche et d'un message si la requête n'a pas abouti (pas de requête ou pas de résultat).
  
.. nextslide:: 
 
* page détaillée d'article :

  - accessible via l'URL (ex : article.php?id=12);
  - affichage du titre, de l'illustration, du texte complet,et de tous les commentaires associés;
  - possiblité d'ajout de commentaire si l'utilisateur est connecté (en tant que "user" ou "webmaster"). L'ajout d'un commentaire doit actualiser la page;
  - chaque commentaire doit afficher le nom de l'utilisateur qui l'a écrit, la date d'ajout et son contenu.
 
.. nextslide:: 
  
* page d'ajout d'article :

  - accessible uniquement si l'utilisateur est connecté en tant que "webmaster";
  - permet de créer et d'ajouter un nouvel article à la base de données (avec tous les champs);
  - affiche des messages d'erreur s'il manque des informations ou un message pour indiquer le bon déroulement de la procédure d'ajout (avec l'URL de l'article ajouté).

.. nextslide::
  
Concernant la structure des pages, chacune devra au minimum comporter :

* une bannière (bandeau supérieur avec le titre du site) ;
* un menu comportant les catégories : accueil, ajouter un article (uniquement si l'utilisateur est connecté en tant que "webmaster"), rechercher un article, à propos;
* un panneau latéral comprenant une zone de recherche ET une zone d'authentification (si l'utilisateur n'est pas connecté) ou les informations et statistiques de l'utilisateur (ex : "connecté en tant que : nom de l'utilisateur, inscrit le xx/xx/xxxx, nombre d'articles écrits (si webmaster), nombre de commentaires (si webmaster/user)") et un lien de déconnexion);
* un pied de page comportant les noms du binôme.

.. nextslide::

Fonctionnalités au choix (1 est à réaliser parmi les suivantes) : 

* **Pagination** sur la page d'accueil faire un système de pagination (1 ... 3 ... 8) et afficher les résumés d'article les plus récents. Limiter le nombre d'articles à 5 par page (page d'accueil). L'affichage doit passer par l'URL (index.php?page=1) et gérer les erreurs.
* **Recherche Avancée** enrichir la fonction de recherche avec des paramètres avancés et implémenter la fonction de recherche évoluée (ex: 5 articles les plus récents ,contenant "mot", écrits par "login").
* **Mode Edition** permettre la modification des articles existants via la même page que pour l'ajout. Et ajouter une date de dernière modification (affichée à la place de la date de création si non vide).
* **Gestion des utilisateurs** créer une page de création de compte utilisateur permettant de s'enregistrer sur le site via un bouton "s'enregistrer" dans la zone d'authentification.

.. nextslide:

**IMPORTANT** :

* La structure des pages devra être la plus modulaire possible (découpez votre page en plusieurs fichiers réutilisés plusieurs fois).
* Vous devez concevoir votre base de données le plus simplement possible en prenant en compte les fonctionalités demandées.
* Accédez toujours à votre base de données (connexion) grâce à une fonction écrite dans un fichier séparé (et inclut dans les pages qui en ont besoin).  


Constitution du binôme
++++++++++++++++++++++++

Vous travaillerez dans le même binôme que celui constitué pour le `projet d'introduction au Web`__.
Le thème de votre blog restera lui-aussi identique.

__ http://liris.cnrs.fr/~mgueriau/wiki/doku.php?id=fr:teaching:iut

Rendu des projets
+++++++++++++++++

Chaque binôme m'enverra par mail (*maxime [dot] gueriau [at] etu.univ-lyon1.fr*) :

* l'URL à laquelle son projet est accessible, et
* l'URL d'un dépôt GIT (par exemple sur `Github`__) contenant les fichiers du projet (et démontrant un minimum d'utilisation),
* Votre base de données exportée au format .sql
* le nom de la fonctionnalité au choix choisie.

avant le **mercredi 13 mai 2015 à 23:59**.
Tout retard entraînera un malus dissuasif sur la note.

__ https://github.com

Quelques indications
++++++++++++++++++++

* Bien sûr, l'implémentation de certaines fonctionnalités va nécessiter d'écrire un peu de HTML/CSS. Limitez ces ajouts au strict minimum et privilégiez l'aspect dynamique (grâce à PHP). 
* Prenez le temps de réfléchir à la structure des tables de votre base de données ; plus elles seront simples et cohérentes, et plus le traitement des données sera facilité.
* Pour l'ajout de fichiers (images d'un article), vous pouvez renommer le fichier reçu (après tous les tests) pour qu'il prenne comme nom l'identifiant de l'article créé. Cela simplifira son affichage par la suite et résoudra les problèmes de doublons. Se référer à la fonction PHP `lastinsertid()`__.
* Vous pouvez réutiliser le votre dépôt GIT (en créant une nouvelle branche) ou en créer un nouveau.

__ http://php.net/manual/fr/pdo.lastinsertid.php



