---
layout: single
title: "[WIP] Projet Party Game Unreal 4.27"
---

# Bienvenue sur le post de mon projet multijoueur sur Unreal 4.27 !

![iy](\assets\images\Unity.png)

**Bonjour !** Et voici l'article de mon projet de Party Game sur Unreal 4

Bonne lecture !

Je vais donc vous présenter mon projet de Party Game , sur lequel je travaille et qui m'a permis d'apprendre beaucoup de choses.

Avant de me lancer dans les explications de ce que j'ai fait, je vais vous expliquer comment j'ai eu l'idée de me lancer dans ce projet.

# La base

Je suis actuellement étudiant, et au cours de ma deuxième année de licence , j'ai découvert le puissant outil d'unreal : les blueprints.

Un moyen très rapide de mettre en place du gameplay , avec beaucoup de facilité, tout ça de manière efficace !

Dès lors que je maîtrisais l'outil, je me suis dit, que c'était très simple pour moi de créer des jeux, juste des maquettes en quelques heures.

J'ai pour habitude de beaucoup jouer avec des amis, et que des fois, arrive soudainement des réflexions de gameplay fun et rapide qui pourrait se faire.

Souvent, ces idées restent que quelques minutes puis disparaisses .

Donc je me suis dit pourquoi pas faire un jeu, qui regroupe toutes ces idées, tout ça en multijoueurs en ligne.(Pour pouvoir jouer avec mes amis à l'autre bout de la france)

Et pour cela, je devais avoir une base de jeu, avec différents gameplay, pour pouvoir présenter l'idée à mes potes pour que par la suite, on puisse y rajouter des jeux dessus.

Tout comme ces Mario Party, ces party games , mais cette fois-ci un jeu à nous, facile d'accès et gratuit (pas de serveur à payer, etc...)

# Le commencement

Je devais donc trouver une solution pour me permettre de jouer avec mon ami qui habite à 800 km, tout ça sans passer par des systèmes payants de serveur.

Et c'est là que Steam Advanced Session arrive !

![Screenshot00](\assets\images\RogueLike_3.PNG)

Ce plugin était fait pour mon projet !

Cela fonctionne très simplement.

Normalement, dans tout système multijoueur , des joueurs pour jouer ensemble doivent se connecter tous sur le même serveur.

Le serveur, c'est une machine qui permet de mettre en relation tous les joueurs et pouvoir y faire de l'échange d'informations.

Un serveur, dans le cas où j'en louerais le service, serait disponible h24 , avec une qualité qui resterais linéaire et peu de problèmes dans le cadre de la fluidité des informations d'une partie.

![Screenshot00](\assets\images\RogueLike_3.PNG)

Or, dans mon cas, je ne voulais pas utiliser ce service, car je ne voulais pas investir d'argent dans ce projet.

J'ai donc utilisé le Steam Advanced Session ! Qui permet à un joueur de faire office de serveur, avec le principe de Hosting .

Sa machine, donc sa connexion va donc faire office de serveur. La stabilité de la partie va donc dépendre de la connexion du host et comme ce n'est pas une machine qui tourne h24 , il suffit que le host ce déconnecte pour que la partie soit interrompue.

![Screenshot00](\assets\images\RogueLike_3.PNG)

Autre inconvénient

Si j'avais voulu créer quelconque système de progression, malheureusement le stockage de ces informations se ferait sur la machine des joueurs et non sur un serveur stocké et vérifié. Donc de la triche aurait pu être possible. Ou même si un joueur change de machine, il ne peut malheureusement pas récupérer sa progression précédente.

Mais peut-être que par la suite, j'intégrerais un serveur seulement pour y stocker la progression des joueurs et permettre un feature quand même sympathique. Cela n'est pas la priorité !

Maintenant, parlons un peu de comment ce présent mon menu, et comment les joueurs peuvent créer leurs parties !

# Le menu et création de partie !

Comme vous pouvez le voir sur ce menu un peu sommaire nous avons plusieurs informations

L'utilisation du Steam Advanced Session nous permet d'avoir accès aux informations steam du joueur , et pouvoir lui attribuer un pseudo et une image de profil !

Cela par la suite nous permet aussi d'avoir accès à la liste d'amis du joueur et d'envoyer des invitations.

Lorsqu'on appuie sur le bouton jouer, on arrive sur une interface.

Ceci est le menu de création et recherche de serveurs.

À droite, une liste va chercher tous les serveurs disponibles que le joueur peut rejoindre.

Et à gauche, le joueur peut créer son propre serveur !

Il peut choisir le nom du serveur, le nombre de joueurs qui peuvent y rentrer et savoir quelle méthode utiliser pour le host.

Sans rentrer dans les détails, le joueur peut se connecter soit en Internet soit en LAN.

Lorsque le joueur créé une session ou rejoins une session, il va arriver sur ce menu.

Les boutons vont être différents si il est un simple client ou bien le host.

Le host va pouvoir changer plusieurs choses dans ce menu :

Tout d'abord le choix du jeu

Puis d'exclure certains joueurs

Il va par la suite pouvoir lancer la partie quand tous les joueurs sont prêt !

Je vais donc pouvoir vous présenter mes premiers prototypes de jeu !
