---
layout: post
title: "[WIP] Projet Rogue Like Unity"
---

# Bienvenue sur le post de mon projet sur Unity

![Unity](\assets\images\Unity.png)

**Bonjour !** Voici un petit résumé du projet Unity sur lequel je travail !

Bonne lecture !

Je vais donc vous présenter mon projet unity sur lequel je me suis lancé pour pouvoir apprendre à créer un gameplay complet , modulaire pour créer des niveaux / items / sorts / monstres... De façon à pouvoir faire un module qui pourra être utilisé pour faire un jeu complet et il suffira juste d'ajouter toute la partie visuel et sonore !

Voici donc les étapes de mon projet avec des explications simples de comment cela peut être utilisé par un game designer par exemple .

# La génération procédural

Tout d'abord j'ai dû créer un système procédural pour faire apparaître des niveaux aléatoirement .

Pour cela j'ai utilisé le Depth First Search , qui permet dans une grille de faire un chemin , cela forme un labyrinthe .

J’y ai donc rajouté par la suite des règles pour pouvoir avoir la main sur l’aléatoire de la création de ce chemin .

![Screenshot00](\assets\images\RogueLike_3.PNG)

Ici le chemin s'est fait sur cette grille .

![Screenshot01](\assets\images\RogueLike_1.PNG)
![Screenshot02](\assets\images\RogueLike_2.PNG)

Ici on peut voir la même taille de grille et un chemin différent !

Et je peux par la suite créer les salles comme bon me semble , tant qu’elle reste dans la taille d’une case .

![Screenshot03](\assets\images\RogueLike_5.PNG)

On peut y changer la taille de la grille.
Et dans la partie surligné , tout d'abord on peut y renseigner le type de salle , celle présente dans les préfabs du projet.
Après on peut y renseigner les positions MIN et MAX dans la grille , et la case obligatory c'est pour savoir si la salle en question est prioritaire dans son apparition ou pas .

![Screenshot04](\assets\images\RogueLike_6.PNG)

Je peux par la suite affiner cet algorithme pour que la taille des salles ne soit plus un problème .

# Le déplacement

Pour ce projet j'ai décider de faire un déplacement avec une caméra top down et le joueur se déplace avec le clique droit !

![Screenshot05](\assets\images\RogueLike_7.PNG)

Pour cela , j'ai utilisé le navMesh , un principe utilisé de base pour le pathfiding , les IA etc ...

Et ici je m'en suis servi pour y faire le déplacement du joueur. Mais pour que cela fonctionne il faut que les surfaces jouables soient calculé et qu'un bake soit effectué.

Malheureusement comme les niveaux se forment aléatoirement les prébakes ne sont pas possible . Donc un bake est éffectué après que le niveau se forme pour que les salles soient liés entre elles.

![Screenshot06](\assets\images\RogueLike_8.PNG)

Le seul inconvénient il faut un temps d'attente avant de pouvoir se déplacer , cela va augmenter le temps de chargement d'un niveau.

# Les sorts

Les sorts font partie du gameplay principal , et mon but c’est de pouvoir en faire une partie customisable par le joueur .

Donc tout d’abord j’ai fait un visuel pour les sors utilisé par le joueur , le cooldown est donc affiché sur le visuel du sort ce qui est plus compréhensible pour le joueur .

![Screenshot07](\assets\images\RogueLike_9.PNG)

J’ai créé un emplacement pour y stocker ses sorts
Et par la suite permettre au joueur de choisir lui même ses sorts faire un système d’amélioration / personnalisation.

![Screenshot08](\assets\images\RogueLike_10.PNG)

La création et customisation de sorts est déjà en place , cela permet d’en créer une infinité tout en changeant les stats de ceux ci très facilement !

![Screenshot09](\assets\images\RogueLike_11.PNG)

Voilà pour l’instant ce qui à été fait sur ce projet
Pleins de choses reste à faire, ce n'est que le début de celui-ci !
