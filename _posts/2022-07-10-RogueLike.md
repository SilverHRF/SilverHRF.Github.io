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

**La génération procédural**

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
