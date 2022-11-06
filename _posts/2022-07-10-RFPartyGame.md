---
layout: single
title: "[WIP] Projet Party Game Unreal 4.27"
---

# Bienvenue sur le post de mon projet multijoueur sur Unreal 4.27 !

![iy](\assets\images\Ue4_Multi\ue4.png){: .align-center}

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

Ce plugin était fait pour mon projet !

Cela fonctionne très simplement.

Normalement, dans tout système multijoueur , des joueurs pour jouer ensemble doivent se connecter tous sur le même serveur.

Le serveur, c'est une machine qui permet de mettre en relation tous les joueurs et pouvoir y faire de l'échange d'informations.

![ScreenShot001](\assets\images\Ue4_Multi\Serveur.png){: .align-center}

Un serveur, dans le cas où j'en louerais le service, serait disponible h24 , avec une qualité qui resterais linéaire et peu de problèmes dans le cadre de la fluidité des informations d'une partie.

Or, dans mon cas, je ne voulais pas utiliser ce service, car je ne voulais pas investir d'argent dans ce projet.

J'ai donc utilisé le Steam Advanced Session ! Qui permet à un joueur de faire office de serveur, avec le principe de Hosting .

Sa machine, donc sa connexion va donc faire office de serveur. La stabilité de la partie va donc dépendre de la connexion du host et comme ce n'est pas une machine qui tourne h24 , il suffit que le host ce déconnecte pour que la partie soit interrompue.

Autre inconvénient

Si j'avais voulu créer quelconque système de progression, malheureusement le stockage de ces informations se ferait sur la machine des joueurs et non sur un serveur stocké et vérifié. Donc de la triche aurait pu être possible. Ou même si un joueur change de machine, il ne peut malheureusement pas récupérer sa progression précédente.

Mais peut-être que par la suite, j'intégrerais un serveur seulement pour y stocker la progression des joueurs et permettre un feature quand même sympathique. Cela n'est pas la priorité !

Maintenant, parlons un peu de comment ce présent mon menu, et comment les joueurs peuvent créer leurs parties !

# Le menu et création de partie !

![ScreenShot002](\assets\images\Ue4_Multi\Cap13.PNG){: .align-center}

Comme vous pouvez le voir sur ce menu un peu sommaire nous avons plusieurs informations

L'utilisation du Steam Advanced Session nous permet d'avoir accès aux informations steam du joueur , et pouvoir lui attribuer un pseudo et une image de profil !

Cela par la suite nous permet aussi d'avoir accès à la liste d'amis du joueur et d'envoyer des invitations.

Lorsqu'on appuie sur le bouton jouer, on arrive sur une interface.

![ScreenShot003](\assets\images\Ue4_Multi\Cap14.PNG){: .align-center}

Ceci est le menu de création et recherche de serveurs.

À droite, une liste va chercher tous les serveurs disponibles que le joueur peut rejoindre.

Et à gauche, le joueur peut créer son propre serveur !

![ScreenShot011](\assets\images\Ue4_Multi\Cap15.PNG){: .align-center}

Il peut choisir le nom du serveur, le nombre de joueurs qui peuvent y rentrer et savoir quelle méthode utiliser pour le host.

Sans rentrer dans les détails, le joueur peut se connecter soit en Internet soit en LAN.

Lorsque le joueur créé une session ou rejoins une session, il va arriver sur ce menu.

![ScreenShot004](\assets\images\Ue4_Multi\Cap16.PNG){: .align-center}

Les boutons vont être différents si il est un simple client ou bien le host.

Le host va pouvoir changer plusieurs choses dans ce menu :

Tout d'abord le choix du jeu.

Puis d'exclure certains joueurs.

![ScreenShot005](\assets\images\Ue4_Multi\Cap17.PNG){: .align-center}

Il va par la suite pouvoir lancer la partie quand tous les joueurs sont prêt !

Je vais donc pouvoir vous présenter mes premiers prototypes de jeu !

Avant de commencer, je vais essayer de simplifier comment un jeu multijoueur fait pour que tous les joueurs puissent voir la même chose ou non.

Pour faire simple dès qu'un joueur fait une action (sauter par exemple) celui-ci va envoyer une information au serveur pour lui dire qu'il saute.

Le serveur récupère cette information, puis l'envoie à tous les autres joueurs, pour que cette information soit vue de tous !

Tout ce qui est animation, déplacement, interaction. Si on veut qu'elle soit vue de tous on doit envoyer l'information au serveur pour que celui-ci le transmette à tout le monde !

Un principe que j'ai dû appliquer à toutes mes étapes, mais que je ne vais pas vous détailler pour chacune, car cela est répétitif dès lors que l'on comprend comme ça fonctionne.

# Capture The flag

Je voulais donc créer un jeu TPS, avec un système d'équipe et de point global.

J'ai donc choisi le principe du Capture the flag, le but récupérer le drapeau adverse dans leur base et le ramener dans la vôtre sans vous faire voler le vôtre !

Dans un premier temps, il m'a fallu créer le choix des équipes !

![ScreenShot006](\assets\images\Ue4_Multi\Cap1.PNG){: .align-center}

Pour cela, les joueurs sont tout d'abord mis en spectateur et doivent rejoindre une équipe avant de pouvoir lancer la partie !

Quand celle-ci ce lance un timer se met en route !

Et la partie peut commencer.

![ScreenShot007](\assets\images\Ue4_Multi\Cap2.PNG){: .align-center}

Pour commencer dans la partie gameplay, j'ai créé le système de tir/visé.

Pour cela, j'y ai ajouté des animations qui permettent de changer d'état, lorsque l'on s'accroupit le joueur est plus lent.

![ScreenShot009](\assets\images\Ue4_Multi\Cap3.PNG)

Ou bien lorsque le joueur vise il à une meilleure vision d'où il tire.

![ScreenShot008](\assets\images\Ue4_Multi\Cap4.PNG){: .align-center}

** Cette partie doit encore être peaufiné , il me reste du chemin pour que cela soit parfait, mais pour du proto ça reste suffisant !**


Pour pouvoir détecter les balles et appliquer les dégâts, j'aurais pu garder la collision de base du character de Unreal !

J'ai donc créer une collision personnalisée, et cela me permet par la suite de choisir le montant des dégâts localisé

{% include image-gallery.html folder="\assets\images\Ue4_Multi\Collision" %}

Avec ça, il ne me restait qu'à créer un système de munitions et de vie des joueurs !

![ScreenShot010](\assets\images\Ue4_Multi\Cap7.PNG){: .align-center}

Dès lors que le joueur n'as plus de balle celui-ci doit recharger (animation qui permet aux autres joueurs que celui-ci recharge)

Et si un joueur venait à ne plus avoir de pv , il meurt, et un UI apparaît pour lui montrer qui l'as tué et un timer avant de pouvoir revenir sur le champ de bataille !

![ScreenShot012](\assets\images\Ue4_Multi\Cap8.PNG){: .align-center}

Maintenant, que le déplacement et le tir sont faits ! Il ne reste que la capture de drapeau !

Pour cela, j'ai y faire des règles simples !

Un joueur bleu peut récupérer le drapeau rouge, dans la base rouge.

![ScreenShot013](\assets\images\Ue4_Multi\Cap5.PNG){: .align-center}

Dès lors que le joueur récupère le drapeau, il l'a sur son dos et des particules apparaisses autour de lui !

![ScreenShot014](\assets\images\Ue4_Multi\Cap6.PNG){: .align-center}

Son objectif le ramenait à sa base pour mettre le point !

S'il meurt lors de ce transport, le drapeau tombe par terre et le plus rapide à le récupérer, dans le cas du drapeau rouge, si un joueur rouge le récupère le drapeau revient à sa base, si c'est un joueur bleu la course repars de plus belle !

![ScreenShot015](\assets\images\Ue4_Multi\Cap9.PNG){: .align-center}

Si le joueur bleu arrive à bon port ! Et que son drapeau lui est toujours présent alors il peut marquer le point !

![ScreenShot016](\assets\images\Ue4_Multi\Cap10.PNG){: .align-center}

Et les drapeaux retournent tous à leurs bases et ne peuvent être récupérés que quelques secondes après la mise du point !

Il ne me reste qu'à vous parler du système de notification que j'ai mis en place, que je pourrais réutiliser par la suite !

J'ai créé un système de structure pour pouvoir y mettre plusieurs informations dans ces notifications.

Pour l'instant au plus simple, avec le texte à envoyer puis la couleur.

![ScreenShot017](\assets\images\Ue4_Multi\Cap11.PNG){: .align-center}

Maintenant comment les notifications sont reçu puis afficher, tout d'abord si aucune notification n'est en cours alors celle-ci va s'afficher et si aucune n'arrive le temps d'affichage alors elle restera affiché le temps maximal donné.

Or, si une notification arrive, on va dire 1 sec après, tout d'abord elle ne va pas s'afficher, mais se mettre dans une liste d'attente, si la liste d'attente et remplis alors les notifications resterons moins longtemps afficher sur l'écran le temps de voir les autres avec pas trop de délais !

![ScreenShot018](\assets\images\Ue4_Multi\Cap12.PNG){: .align-center}

Un système assez simple et puissant que je pourrais modifier à ma guise par la suite !

C'est à peu près tout ce que j'ai mis en place pour l'instant pour ce prototype.

Il ne reste plus qu'à itéré des maps de jeu !



Je suis encore sur l'élaboration d'autre proto de jeu que je vous montrerai plus tard !

Merci d'avoir lu !