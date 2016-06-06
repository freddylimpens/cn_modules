LANGUAGE:   fr
TITLE:   Les traitements et les applications
MENUTITLE: Les traitements
AUTHOR:     Culture numérique
CSS: http://culturenumerique.univ-lille3.fr/css/base.css

# Comprendre les traitements

Pour être un utilisateur averti et un acteur dans notre monde numérique, il est utile de comprendre pourquoi les ordinateurs peuvent nous paraître parfois plus précis, rapide ou efficaces  que nous,  voire même intelligents. Nous savons tous qu'ils peuvent calculer très vite, et donc traiter rapidement de grandes quantités de données. C'est un premier élément de compréhension, mais qui ne suffit pas. Une explication complémentaire est leur capacité à réaliser des traitements complexes  en combinant des traitements de base très simples. Cette combinaison, c'est nous qui la commandons et la décidons. Si bien qu'on retrouve dans cette "intelligence informatique" des ordinateurs toute l'ingéniosité des femmes et des hommes qui les ont programmés. 

Dans cet objectif, nous allons étudier comment les applications fonctionnent, comment elles sont construites, comment elles se coordonnent et comment elles manipulent des données complexes.

Pour introduire ce cours, considérons l'exemple de calcul d'itinéraire par un logiciel sur un site Web, une application mobile ou encore un petit ordinateur spécifique (qu'on appelle abusivement GPS).  Tout d'abord, réfléchissons aux informations que doit posséder ce logiciel. Tout d'abord, il doit connaître le point de départ, qu'il peut parfois obtenir par des dispositifs techniques (une puce GPS, la connexion réseau) ou qu'il peut vous demander explicitement. Il doit connaître le point d'arrivée et le moyen de transport. Supposons, pour simplifier la présentation, que le logiciel dispose d'une ville de départ, d'une ville destination et que le moyen de transport choisi est la voiture.  Peut-il disposer de la liste de tous les itinéraires possibles entre ces deux villes quelconques ? La réponse est négative car cela nécessiterait bien trop de ressources de stockage. Il dispose uniquement des connexions directes entre villes voisines (la liste des routes en fait), ce qui représente déjà un grand volume mais qui peut être stocké dans un petit équipement comme un smartphone. Un programme ne peut pas non plus calculer tous les itinéraires possibles entre les deux villes que vous avez choisies car le temps de calcul serait trop long et vous n'allez pas de Lille à Paris en passant par Marseille ! Donc ce programme se doit d'être plus "intelligent" et calculer vite ne suffit pas.

C'est un programme qui va calculer les itinéraires les plus courts ou les plus rapides à partir de cette connaissance des distances directes (sans ville étape) entre deux villes. Ce programme va utiliser un algorithme dit de recherche de plus court chemin, issu des travaux de recherche de mathématiciens et informaticiens ayant étudié ce problème. Cet algorithme est ingénieux. Alors qu'on pourrait s'attendre à devoir comparer tous les chemins de longueur 3 (les triplets de villes), puis 4 (les quadruplets de villes),...  le temps d'exécution sera d'un ordre de grandeur proche du nombre de couples de villes. Comme tous les algorithmes, il consiste à enchaîner et répéter des opérations très simples comme comparer des valeurs numériques, les ajouter, les mémoriser, ces valeurs représentant des villes ou des distances. Mais le génie n'est pas dans l'algorithme mais bien dans ceux qui l'ont conçu, trouvé cette représentation des villes et des distances et qui l'ont exprimé à l'aide de  cette combinaison d'opérations simples.

Notre étonnement à propos des logiciels et des ordinateurs va grandissant quand on combine des calculs comme celui d'un itinéraire avec d'autres calculs pour la reconnaissance vocale, la géolocalisation etc. L'ensemble combiné va former des solutions complètes qui analysent le son de votre voix, le transforment en mots et phrases, y retrouvent suffisamment de sens pour identifier des villes et des rues, des adresses de départ ou de destination, et vous indiquent le chemin le plus rapide en fonction du trafic. À ce stade, le logiciel est devenu un assistant qui peut dépasser les capacités de votre passager uniquement accompagné de ses connaissances et sa carte routière. 

En premier lieu, cet exemple montre qu'exécuter une application
implique l'exécution de nombreux programmes en interaction avec
l'environnement (utilisateur, périphériques, réseau). Il montre
également qu'une application est construite en composant d'autres
applications : récupérer les données saisies, extraire le nom de la
ville, calculer un itinéraire, ... C'est ce principe de composition
qui permet de passer d'une machine "bête" manipulant des 0 et des 1 à
une machine "intelligente" réalisant des applications complexes. C'est
également ce principe de composition qui permet de définir des
algorithmes pour résoudre des problèmes. L'exemple a également permis
de montrer que malgré les capacités sans cesse croissantes des
machines, il faut être attentif à la taille des données mémorisées et
au temps de calcul des programmes. Enfin, on peut noter que
l'intelligence supposée de la machine est due à l'intelligence des
hommes et femmes ayant conçu les applications.

Dans la suite du cours, nous présentons comment composer des
opérations pour définir de nouvelles opérations et discutons des
algorithmes, nous présentons les langages de programmation et la
traduction des algorithmes en programmes et nous montrons comment les
machines gèrent le fonctionnement de toutes ces applications. Nous
terminons par l'étude de quelques exemples : comment un correcteur
orthographique peut-il corriger vos fautes, comment le navigateur
affiche-t-il une page en partant d'un document `html`, et comment une
machine peut-elle jouer aux échecs.


# Les algorithmes 

## Les algorithmes, les langages et la machine

Le mot algorithme a fait irruption dans les médias après que des avancées notables ont été réalisées dans le domaine de l'informatique et ont affecté la société. C'est par exemple la naissance de l'internet et ensuite des moteurs de recherche qui ont posé la question de société de l'accès à la connaissance et des monopoles économiques dans ce domaine:  "Quel algorithme est donc responsable du choix de l'ordre dans lequel les résultats apparaissent".  Mais comprendre ce qui se cache derrière ce mot algorithme ne peut être compris sans comprendre comment l'ordinateur fonctionne en tant que machine et comment on interagit avec lui par le langage. 

Le langage doit permettre de représenter des données, mais également des traitements. Nous l'avons abordé dans le module précédent à travers la question de la numérisation des données. Le langage, c'est pluriel et artificiel : il existe de nombreux langages informatiques, inventés par l'homme, et faisant souvent l'objet de normes ou de standards,  parfois de brevets ou parfois laissés libres d'accès et d'évolution à la communauté. Ce qui les distingue des langages (ou langues) naturels (naturelles), c'est qu'ils ont été conçus pour qu'une machine les interprète et non un être humain. Ils doivent donc être précis, formels, plus encore même que la notation musicale qu'on a toujours la possibilité d'interpréter librement. 

```activité
le rôle des linguistes : qui a inventé le mot ordinateur, qui est larry wall, noam chomsky...{}
```

La machine c'est l'ordinateur. Le mot inventé par un linguiste dans les années 50, fait référence à l'exécution d'ordres, d'instructions. En anglais le mot computer fait plutôt référence au calcul et les deux notions se retrouvent dans cette machine. Essentiellement la machine repose sur une *unité de calcul* qui fonctionne avec des valeurs représentées par des 0 et des 1. Elle utilise des *mémoires* pour retrouver ou ranger ces valeurs à des emplacements précisé par des numéros : les adresses. Enfin une *unité de contrôle* donne les ordres à l'unité de calcul et aux mémoires. Ce modèle abstrait de machine n'a pas bougé depuis les années 40. Il n'est peut être pas si simple de comprendre comment le réaliser physiquement mais plusieurs l'ont fait depuis le premier dans les années 40, parfois par défi, avec des objets mécaniques du quotidien. L'électricité,  puis l'électronique et  la miniaturisation ont considérablement réduit la taille et augmenté la rapidité de la mémoire,  de l'unité de calcul et l'unité de contrôle. Ces progrès l'ont aussi rendu plus économe et plus résistant. 

```activité
Trouver le schéma de l'architecture von neumann. {}
```
## L'illustration par le symbole

Rappelez-vous les conventions de langage dont nous avons parlé au module précédent, introduites pour représenter les caractères. Le caractère A majuscule a
pour nom "Latin Capital Letter A" et pour numéro 65.  Croyez-nous, en binaire ce 65 s'écrit 01000001.  Le caractère a minuscule a pour numéro 97. En binaire cela s'écrit 01100001. C'est remarquable car c'est juste le 6eme chiffre partant de la droite, un 0,  qui est transformé en 1 pour passer de l'un à l'autre. Et cela est vrai pour toutes les lettres de notre alphabet latin. D'un point de vue arithmétique, l'interprétation du changement de ce 6ème chiffre est simplement d'ajouter ou retirer 32 au numéro. 65 +32 fait bien 97. 

Ce choix de représentation, donc de langage pour représenter les symboles est donc très lié au fonctionnement binaire de la machine et à ses capacités de calcul arithmétique. C'est là l'ingéniosité des personnes qui ont conçu ce langage de représentation des symboles. À partir de cela, on peut facilement imaginer le traitement que doit réaliser la machine pour transformer un symbole stocké dans sa mémoire de majuscule en minuscule. Il suffit d'indiquer l'adresse où ce symbole est stocké. Imaginons que ce soit l'adresse 413. 

    Accéder à la mémoire à l'adresse 413 (retrouver la valeur binaire correspondant au code d'un symbole)
	Ajouter 32 (c'est-à-dire, dans l'unité de calcul,  changer le 6ème chiffre de 0 en 1.)
	Ranger le résultat dans la mémoire 413 

L'unité de contrôle doit juste assurer que ces 3 instructions soient réalisées successivement dans cet ordre, *en séquence*. Nous n'irons pas dans les détails du langage numérique inventé pour représenter ces 3 instructions, ce n'est pas très important ici. Par contre, les  notions importantes à retenir sont les suivantes. Premièrement nous sommes parvenus à créer un traitement qui porte un sens pour nous, à partir de la représentation numérique d'une information et grâce à une combinaison d'instructions. Deuxièmement, l'ordonnancement en séquence des instructions constitue le premier outil de combinaison. Nous venons de décrire un algorithme simple ! 


## Et si ce n'était pas une lettre majuscule ?

L'ordinateur est d'abord une machine très obéissante et exécute scrupuleusement les ordres qu'on lui donne. Le traitement précédent ajoutera 32 au numéro même si celui-ci n'est pas le numéro d'une lettre majuscule. Par exemple le numéro 64 représente l'arobase @  et si on lui ajoutait 32 cela donnerait une apostrophe inversée (`).  Pour contrôler cela, il faut introduire une vérification que nous pouvons décrire comme :

    Accéder à la mémoire à l'adresse 413 
	Si la valeur est comprise entre 65 et 90 Alors 
       Ajouter 32 
	   Ranger le résultat dans la mémoire 413 

Parmi les instructions de base que l'unité de calcul sait faire, outre les opérations arithmétiques, nous disposons aussi des comparaisons. 
Le *si* que nous venons d'utiliser très naturellement est la deuxième façon de combiner des instructions. Remarquez que l'algorithme utilise à la fois des *séquences* et un *si*. C'est une combinaison qui permet de considérer différentes  *alternatives* dans le déroulement de l'algorithme, sous certaines conditions. 

## Et pour un texte complet ?

Supposons maintenant que ce soit un texte complet que nous voulons mettre en majuscules... Là encore c'est une articulation entre langage de représentation, machines et algorithmes que nous allons illustrer. Dans un premier temps, il faut choisir une représentation du texte. Ce sera une suite de symboles stockés dans la mémoire les uns à la suite des autres et terminés par un symbole spécial représenté en binaire par 0000000. Ce choix de représentation n'est pas normalisé mais est souvent utilisé. De plus, du point de vue de la machine,  l'unité de calcul permet de faire des opérations sur les valeurs aussi bien que sur des adresses (qui sont aussi des valeurs). L'algorithme lui s'écrira :

    L'adresse courante est 413
    Accéder à la mémoire à l'adresse courante
	Répéter tant que la valeur n'est pas 0000000
  	   Si la valeur est comprise entre 65 et 90 Alors 
          Ajouter 32 
	      Ranger le résultat dans la mémoire à l'adresse courante
       Ajouter 1 à l'adresse courante 
       Accéder à la mémoire à l'adresse courante 

Voilà la troisième manière de combiner des instructions : la répétition. Les informaticiens l'appellent *la boucle*, ou *l'itération*. 



## Les trois combinaisons

Rappelons un petit point d'étape. Machines,  langages (incluant la représentation numérique de l'information et des traitements), et algorithmes sont intimement liés, dépendants.  Autrement dit,  comprendre l'une de ces notions demande d'avoir aussi quelques notions à propos des autres. Les ordinateurs depuis leur création dans les années 40 suivent tous une même organisation qui comprend une unité de calcul de la mémoire et une unité de contrôle. C'est l'architecture de von Neumann. Nous avons illustré ce fonctionnement sur une tâche simple de passage d'un texte en majuscule et mis en évidence 3 structures de combinaison d'instructions qui peuvent être traduites dans l'unité de contrôle: la séquence qui fait passer à l'instruction suivante, l'alternative qui permet de choisir la prochaine instruction selon la valeur d'un test et la répétition d'instructions tant qu'un test est satisfait. 

Une grande force de ces combinaisons est qu'elles s'appliquent sur des instructions de base de la machine comme consulter la mémoire ou réaliser une opération arithmétique, mais aussi sur d'autre combinaisons. L'exemple précédent l'illustre bien. Nous avons une séquence de mémorisation, suivie d'un accès à la mémoire et suivi ensuite par une répétition. La répétition comprend elle-même une alternative suivie en séquence par une opération arithmétique et un accès à la mémoire. 

C'est un vrai jeu de construction! À la manière des Legos où partant de briques de bases, par assemblage on construit des maisons et des villes, on est devant un univers infini de possibilités, pourvu que vous ayez autant de  briques que voulu, où toute votre créativité peut s'exprimer. 

Dans le monde informatique, au fur et à mesure de ces combinaisons, les traitements deviennent de plus en plus impressionnants et puissants. Mais les principes de base restent identiques. Par exemple dans le cas de notre application d'assistance routière, nous retrouvons la composition en séquence de la reconnaissance vocale des directions, le calcul d'itinéraire et son affichage. L'alternative permet, si le lieu d'arrivée n'est pas connu, d'afficher un message plutôt que l'itinéraire. L'itération est la combinaison qui permet la répétition des annonces vocales tant que vous n'êtes pas arrivé... 

## Calculer et calculable 

À partir des instructions de base de la machine, on construit donc des traitements par un algorithme en utilisant les trois modes de composition que sont la séquence, l'alternative et l'itérative. Est-ce suffisant ? Oui car il existe un **théorème** qui affirme que tout ce qui est calculable avec une machine peut être défini par quelques opérations élémentaires et les opérations de composition que sont la suite (ou la séquence), l'alternative et l'itérative. Ce théorème a été démontré au milieu du vingtième siècle par des mathématiciens et des logiciens. Ceci soulève immédiatement la question : une machine peut-elle tout calculer ? La réponse, démontrée à la même époque, est négative : il existe des problèmes que ne peut pas résoudre une machine. Par exemple, il est montré qu'il n'existe pas d'algorithme qui prend en entrée une suite d'instructions contenant des alternatives et des itératives et qui répond en sortie cette suite d'instructions va s'arrêter en un temps fini lorsqu'on l'exécutera. Ces sujets soulèvent des problèmes importants qui ont été et sont encore étudiés par les mathématiciens, les informaticiens, les logiciens et les philosophes. Notons enfin, que savoir qu'un problème est calculable ne suffit pas à savoir le traiter car le temps de calcul peut être prohibitif.

### Les algorithmes

Nous utilisons tous, plus ou moins consciemment, des algorithmes plus
ou moins précis dans notre quotidien : pour réaliser des calculs, pour
organiser un déplacement, pour organiser notre journée de travail,
pour réaliser une tâche complexe. Par exemple, pour aller à pied de
mon domicile à un restaurant dont je connais l'adresse, je vais suivre
des rues, tourner à certaines intersections et parcourir la rue du
restaurant jusqu'à arriver devant sa porte selon un algorithme que je
me suis fixé, quitte à l'adapter si je me trompe en chemin. Nous
pouvons noter que nous n'utilisons pas tous le même algorithme et même
que je peux choisir un algorithme différent selon la météo, ma
connaissance de la destination, mon humeur ... Quant aux machines, les
algorithmes devront être définis de façon très précise en prévoyant à
l'avance toutes les situations possibles. Il existe également
plusieurs algorithmes possibles pour résoudre un même problème. Le
choix sera effectué en fonction des compétences du concepteur et de
contraintes comme l'efficacité de l'algorithme mesurée par le temps de
calcul.


```activité
::Modèle de machine::
[markdown]
**Modèle de machine**
Proposer une ressource simple et poser des questions sur modèle de Von Neuman
```

```activité
::Les minuscules en majuscules::
[markdown]
**Les minuscules en majuscules**
On souhaite apprendre à la machine à faire la transformation inverse, à savoir transformer les minuscules en majuscules. 
- Pour transformer un caractère minuscule en majuscule, quelle instruction faut-il changer dans `Maj2MinCara` ?
- Pensez-vous qu'on puisse apprendre à une machine à faire cette nouvelle instruction ?
- Expliquez ce qu'il faut changer dans `Maj2MinChaine` pour obtenir un programme `Min2MajChaine` qui prend en entrée une séquence de caractères et qui transforme les minuscules en majuscules et laisse tous les autres caractères inchangés.
{#### retirer 32 au code au
lieu d'ajouter 32 ; oui, on doit pouvoir apprendre à notre machine à
faire une soustraction de deux entiers même si cela semble un petit
peu plus compliqué que l'addition ; tester si le code du caractère est entre 97 et 123 et appeler le programme qui transforme minuscule en majuscule.}
```

```activité
::Robot::
[markdown]
**Programmer un robot simpliste**
Activité sur le robot ?
```

```activité
::Plusieurs algorithmes pour un même problème::
[markdown]
**Plusieurs algorithmes pour un même problème**
Deux algorithmes sur des chaines de caractères : un efficace et un pas efficace
```

```compréhension
::Conception des algorithmes::
[markdown]
**Conception des algorithmes**
 Pour résoudre un problème il existe un seul algorithme{F}
 
::Exécution de programmes::
[markdown]
**Exécution de programmes**
Des exemples simples de programmes robot pour demander situation finale
```

# Conception des programmes
## Algorithmes, programmes et langages

Nous avons vu que l'on pouvait composer des instructions de base pour définir des traitements. Ces traitements peuvent être à leur tour considérés comme de nouvelles instructions qui pourront à leur tour être composés pour créer des traitements plus complexes. Une telle composition est un algorithme qui fondamentalement décrit un traitement qui permet de résoudre un problème. L'algorithme décrit comment on transforme les données qu'on lui présente, les entrées d'un problème,  pour fournir un résultat. 

Un algorithme est conçu par une femme ou un homme mais doit ensuite être traduit pour pouvoir être exécuté par une machine. Pour cela, il faut traduire l'algorithme dans un langage compréhensible par la machine. Il faut donc disposer d'un langage commun entre l'humain et la machine. 

Il existe, en réalité, de nombreux langages dépendant du mode d'interaction entre l'humain et la machine. Vous pouvez, par exemple, interagir avec une application par un langage graphique à base de menus ou par des clics de souris ou par l'action de frapper sur des touches de clavier. Pour apprendre à vous servir d'une application, vous allez apprendre ce langage : quelle est l'action réalisée par le choix de cet élément de menu, quelle est l'effet d'un clic de souris sur cet élément, quel est l'effet de l'appui sur cette combinaison de touches. Plutôt qu'un langage d'actions, on peut préférer utiliser un langage écrit. C'est, par exemple, le cas pour les langages de description de documents comme `html`, de description d'images ou de descriptions de sons.

Lorsqu'il s'agit de traduire un algorithme, c'est-à-dire expliquer à la machine une combinaison d'instructions, on utilise des langages écrits appelés **langages de programmation**. Il en existe de nombreux, le choix va dépendre des fonctionnalités de base du langage, des besoins de l'application, des performances souhaitées, ... Les textes écrits dans ces langages sont des **programmes** qui sont la traduction d'algorithmes dans le langage choisi. Ces langages et les programmes se doivent d'être compréhensibles par l'informaticien(ne) mais comme ils sont destinés à être exécutés par la machine, ils respectent des règles très strictes de syntaxe. Ceci explique qu'une machine va refuser une commande mal écrite alors qu'un humain acceptera une phrase mal formée dès qu'il en comprend le sens. Cette rigueur nécessaire et la difficulté d'apprendre un langage de programmation effraient beaucoup de monde. Cependant, il est important de remarquer que le plus difficile est de concevoir un algorithme alors que programmer n'est que traduire un algorithme dans un langage.


## Créer de nouvelles applications

Aujourd'hui, la plupart des besoins, personnels ou professionnels, des
utilisateurs sont couverts par une ou plusieurs applications ce qui
fait dire, à tort, à certains qu'il est inutile de comprendre comment
sont conçues des applications. Nous pensons, a contrario, que bien
comprendre le fonctionnement des machines et des applications permet
de se poser les bonnes questions, de comprendre le fonctionnement des
applications et de pouvoir choisir la meilleure application en
fonction des besoins et de critères sociaux, financiers, d'usage ou
autres. De plus, il se peut qu'un besoin ne soit pas couvert et, dans
ce cas, il sera nécessaire de développer ou faire développer une
nouvelle fonctionnalité adaptée.

Concevoir une application est une tâche de haut niveau qui requiert de
nombreuses qualités comme savoir organiser des données, concevoir des
algorithmes, organiser les traitements, répondre aux contraintes
d'efficacité, de mémoire. Elle demande aussi en premier lieu de
répondre aux besoins de l'utilisateur, à des contraintes
organisationnelles ou légales et donc d'être en capacité de rédiger un
cahier des charges. On parle d'*analyse informatique* et de *génie
logiciel* pour désigner la science de concevoir des
applications. C'est une tâche souvent réalisée en équipe où des
informaticiens doivent interagir régulièrement avec des utilisateurs
et des experts métier. Il existe de nombreuses méthodes de
conception. Les plus récentes sont les *méthodes agiles*
alternant phases de conception, phases de développement, phases de
mise en oeuvre et de retour des utilisateurs.

Les phases de développement sont souvent abordées selon deux principes
de conception : une méthode ascendante ou descendante.  Rappelez-vous
toutefois qu'on conçoit d'abord des algorithmes avant de les traduire en programme dans le langage choisi.

Le principe de la **conception ascendante** est de créer de nouvelles
fonctionnalités qui peuvent, à leur tour, être considérées commes des
fonctionnalités de base ce qui permet de recommencer le processus pour
créer de nouvelles fonctionnalités encore plus riches. 

Le principe de la **conception descendante** est de construire une
application ou une nouvelle fonctionnalité en décomposant le problème
en des problèmes plus simples. Notons que c'est une démarche
courante. En effet,si je dois me rendre de mon domicile à Lille à
l'hôtel Arosfat à Londres par le train, je vais décomposer le problème
en problèmes plus simples : aller de mon domicile à la gare TGV,
prendre le TGV, aller de la gare St Pancras à l'hôtel. On peut alors
continuer le processus de décomposition. Par exemple, aller de la gare
St Pancras à l'hôtel peut se décomposer en : se rendre au terminus des
navettes, si une navette est disponible rapidement, prendre la
navette, sinon se rendre au métro, ... On arrête la décomposition
lorsque tous les sous-problèmes introduits correspondent à des
fonctionnalités de base de notre langage. 




```activité
::Algorithmes et programmes::
[markdown]
**Algorithmes et programmes**
Un algo qui affiche 5 fois "Hello World" traduit dans différents langages
```

```activité
::Langages de programmation::
[markdown]
**Langages de programmation**
Il existe de nombreux langages de programmation. En voici quelques exemples

* pour apprendre en s'amusant : lien sur scratch
* pour la conception artistique : lien vers processing
* pour le Web : lien vers javascript
```


```compréhension
::Algorithmique et programmation::
[markdown]
**Algorithmique et programmation**
Le plus difficile est-il de concevoir l'algorithme ou de traduire l'algorithme en programme ? {concevoir algo}
```

# Machines et applications - Choisir une application

### Introduction

Nous avons vu qu'une application telle que vous l'utilisez est
constituée d'un ensemble de programmes. Un programme est la traduction
dans un langage compréhensible par la machine d'algorithmes très
précis. Chaque programme peut donc être vu comme une composition
d'instructions de commandes à la machine. Ceci explique le
comportement "bête" des machines et des programmes qui ne savent
qu'appliquer des consignes apprises dans des contextes prévus. En
particulier, un programme vous enverra un message d'erreur dès qu'il
rencontrera des conditions inconnues pour lesquelles on ne lui a pas
expliqué ce qu'il devait faire.

D'un autre point de vue, les machines nous paraissent "intelligentes"
pour, au moins, deux raisons. La première est le nombre impressionant
d'applications à notre disposition dans le monde numérique : pour
communiquer, pour chercher de l'information, pour écouter de la
musique, pour regarder des vidéos, pour composer de la musique, pour
dessiner, pour composer des textes ou des pages Web, pour faire des
calculs, ... la liste est trop longue ! La seconde est que la machine
contient tout un ensemble de couches applicatives qui fait que nous
utilisons des applications avec des fonctionnalités de très haut
niveau en oubliant complètement tous les aspects matériels. En
particulier, nous oublions comment est gérée la mémoire, comment
s'exécutent les opérations de base, comment les données sont
sauvegardées sur disque, comment sont transmises les informations sur
le réseau, ...

Nous allons, dans cette section, présenter les grandes lignes de la
gestion des applications et des données par les machines et discuter
du choix d'une application.

### Le système d'exploitation

Le système d'exploitation est la première couche logicielle de tout
ordinateur qu'il soit fixe ou portable ou tablette ou smartphone. Il
cache toute la complexité des calculs en binaire au niveau matériel
(vous vous en moquez), la façon dont il range les données dans les
mémoires (il faut qu'il retrouve ce que vous lui demandez), la façon
dont il gère l'exécution des programmes que vous lancez (il faut que
mes applications fonctionnent, plusieurs en même temps) et la façon
dont il gère toutes les entrées-sorties, c'est-à-dire toutes les
communications avec les périphériques (il saisit ce que je tape au
clavier, il comprend mes clics, il affiche sur l'écran, il envoie mes
impressions à l'imprimante, il échange mes données sur le réseau).
Vous vous moquez de la façon dont il travaille mais vous l'utilisez
souvent pour lancer vos applications, pour sauvegarder vos fichiers de
travail, pour vous connecter au réseau, pour installer un nouveau
périphérique. Il se présente comme une interface graphique (depuis les
années 90) avec principalement : un gestionnaire de fichiers, un
gestionnaire d'applications et un gestionnaire de configuration du
système.

Le **gestionnaire de fichiers** gère toutes vos données numériques. En
effet, *tout est fichier*, c'est-à-dire que les données et les
applications sont toutes rangées dans des fichiers. Malgré certaines
tentatives, on n'a pas encore trouvé mieux que de ranger les fichiers
dans des boîtes qui sont elles-mêmes contenues dans des boîtes qui
... Ces boîtes sont appelées dossiers ou répertoires. Donc, les
fichiers sont organisés dans une hiérarchie de répertoires, chaque
répertoire contenant des fichiers et/ou des répertoires. Il faut
comprendre que l'on peut se déplacer dans cette hiérarchie avec des
commandes ou en ouvrant le répertoire en mode graphique par un double
clic. Le répertoire dans lequel on est à un instant donné s'appelle le
répertoire courant. Le sommet de la hiérarchie s'appelle la racine,
c'est souvent l'endroit où vous êtes placés en début de session.  Les
fichiers sont désignés par un nom souvent de la forme
`prefixe.suffixe`, le suffixe est souvent lié à une application comme
`rapport.doc` ou `mapage.html`. Dans une utilisation courante, il est
conseillé de nommer vos fichiers (et répertoires) avec des noms qui
ont un sens (une sémantique), d'utiliser le bon suffixe (il est
parfois ajouté automatiquement par le logiciel), d'éviter les espaces
et les accents dans les noms et de ranger vos fichiers dans un
répertoire où vous saurez le retrouver. Pour désigner un fichier, il
faut préciser son nom et où il est rangé.

Le **gestionnaire des tâches** gère les exécutions des
applications. Il vous permet sur ordinateur de lancer plusieurs
applications simultanément, de basculer d'une application à l'autre
soit par des combinaisons de touche soit en cliquant dans la barre des
tâches, d'arrêter l'exécution d'une application, ... Sur un
ordinateur, il faut savoir que, sans que vous en soyez conscients, il
y a un grand nombre de tâches qui s'exécutent en particulier pour que
vos applications interagissent avec vous et les périphériques que sont
clavier, souris, écran et réseau. 

Le système d'exploitation assure bien d'autres missions comme, par
exemple, la gestion des périphériques, la gestion des utilisateurs
quand on est plusieurs à utiliser une même machine, la gestion des
droits pour protéger les données des utilisateurs.

### Les applications

Comme dit dans l'introduction, les applications à notre disposition
sont nombreuses. Pour un même problème, plusieurs applications sont
souvent disponibles. Comme utilisateur, dans votre vie personnelle,
vous êtes amenés à choisir une application pour votre ordinateur ou
téléphone portable. Dans votre vie professionnelle, vous serez amenés
à choisir ou à participer au choix d'une application. Ce peut être,
par exemple, le choix d'un logiciel de production de documents écrits,
le choix d'un logiciel de dessin, le choix d'un logiciel de conception
de sites Web, le choix d'un langage de programmation, ... Nous
étudions ici quelques critères principaux participant au bon choix
d'une application pour un problème donné.

* **contraintes techniques : ** la machine utilisée et son système
  d'exploitation en usage personnel, environnement matériel et
  logiciel en usage professionnel
* **critères d'usage : ** vos compétences ou les compétences des
  utilisateurs, les habitudes de travail
* **fonctionnalités : ** point essentiel de correspondance entre les
  besoins, exprimés dans un cahier des charges en contexte
  professionnel, et les possibilités apportées par le logiciel. Cette
  étude peut être complexe. Par exemple, pour choisir une application
  de conception de site Web de nombreuses fonctionnalités sont à
  mettre en rapport avec les besoins : mise à jour du site, nombre
  d'usagers, gestion de newsletter, gestion de forums, gestion de
  paiement en ligne, ... 
* **type de logiciel : ** nature de la licence, possibilité de
  développements propres, support fourni (aide à l'installation,
  conseil, formation, existence de forums, ...), maintenance du
  logiciel, son évolutivité 
* **prix : ** prix incluant les coûts éventuels de support, formation,
  maintenance et de mise à jour. Prévoir également des coûts matériels
  et logiciels dérivés.

Cette liste de critères ne prétend pas être exhaustive. Les critères
ne sont pas indépendants et le choix correspondra en la recherche du
meilleur compromis entre les besoins et les possibilités fournies par
l'application.

```activité
::Systèmes d'exploitation::
[markdown]
**Systèmes d'exploitation**
Discuter des systèmes pour

* pour ordinateur
* pour smartphone
```

```compréhension
::Représenter et manipuler::
[markdown]
**Représenter et manipuler**
Les traitements possibles dépendent fortement des choix de représentation
{T}
```

# Exemples d'algorithmes et applications

Dans cette section, nous présentons le fonctionnement de trois
programmes. Pour chacun d'eux, un premier objectif est de vous faire
comprendre les algorithmes qui sont derrière ces applications, de vous
montrer que cette compréhension vous permet de savoir ce que vous
pouvez attendre de l'application, c'est-à-dire comprendre ce qu'elle
peut faire et ne peut pas faire. Un second objectif est de vous
montrer les choix du concepteur de l'application et leur influence sur
les possibilités de traitements et leur efficacité. Le dernier exemple
introduit, par l'exemple d'un jeu, un algorithme plus sophistiqué issu
du domaine de l'intelligence artificielle.

### Un correcteur orthographique en français

Certains traitements de texte incluent une fonctionnalité de
correction orthographique. Dans sa forme la plus simple, la correction
se fait pour chaque mot indépendamment de son contexte, autrement dit
sans tenir compte des règles de grammaire comme pour l'accord et la
conjugaison. Le correcteur vérifie que tout mot du texte est une forme
correcte d'un mot de la langue française. 

Un texte est une séquence de caractères. Il faut tout d'abord définir
la notion de mot. Pour cela, un algorithme naif est de considérer
qu'un mot est toute suite de lettres encadrée par des caractères qui
ne sont pas des lettres. Cet algorithme est mis en échec par des mots
comme aujourd'hui ou comme les mots composés qui seraient décomposés
en plusieurs mots. Cet algorithme peut être amélioré et nous supposons
disposer d'un algorithme définissant la notion de mot. Nous pouvons
alors considérer que notre texte est une séquence de mots.

Comment le correcteur peut-il fonctionner ? Tout d'abord, il se doit
de posséder la ressource constituée d'une liste de tous les mots de la
langue française avec leurs formes conjuguées et accordées. Il dispose
également d'une liste de non mots comme les noms propres, les
abbréviations, les sigles, ... Le correcteur ayant ces deux ressources
à sa disposition, nous pouvons proposer l'algorithme suivant :

`Correcteur orthographique`

1. **en entrée** : une séquence de mots
2. **pour** tous les mots de la séquence d'entrée
3. chercher le mot dans la liste des mots et dans la liste des non mots
4. **si** il n'existe pas **alors**
5. le souligner
6. **fin du si**
7. **fin du pour**
8. **en sortie** : la séquence de mots avec des mots soulignés qui
   sont considérés comme mal orthographiés

Cet algorithme met-il en évidence toutes les fautes d'orthographe ?  Il
souligne et donc considère comme mal orthographiés tous les mots du
texte qui n'apparaissent ni dans la liste des mots, ni dans la liste
des non mots. Quelles sont les erreurs possibles de cet algorithme ? Une
première erreur possible est de souligner à tort un mot parce que les
listes sont incomplètes comme, par exemple, un nom spécifique à un
domaine ou un nom propre non répertorié. Une seconde erreur possible
est de ne pas souligner un mot parce que l'erreur est due à une faute
d'accord ou de conjugaison comme "la vache bleu" ou "je montres".

Cet algorithme est-il efficace en temps de calcul ? Le parcours de
tous les mots étant obligatoire, l'efficacité de notre
algorithme dépend de la vitesse de recherche de chacun des mots dans
les listes. En effet, la taille de chacune des listes est de l'ordre
de plusieurs centaines de milliers de mots. Le parcours des listes en
séquence prendrait trop de temps, il est donc nécessaire de définir
des méthodes de recherche plus rapides, méthodes qui sont étudiées
dans le module sur la recherche d'information.

Comment améliorer la qualité de la correction orthographique de notre
correcteur ?  Une première piste est d'avoir des listes de mots les
plus complètes et les plus actuelles possibles. Une seconde piste est
d'enrichir les compétences du correcteur avec la correction
grammaticale. Une première possibilité est de doter le correcteur de
la capacité d'analyser votre phrase pour répondre aux questions telles
que : quel est le sujet du verbe ? Avec qui s'accorde cet adjectif ?
Ayant analysé, il doit également connaître les règles orthographiques
et être capable de vérifier qu'elles sont correctement appliquées. La
difficulté est ici de réaliser ces analyses car ils nécessitent une
grammaire numérisée de la langue et des programmes d'analyse. Une
seconde possibilité est d'utiliser des méthodes dites "force brute"
qui, au lieu de mémoriser des listes de mots, mémorisent des listes de
couples de mots, de triplets de mots voire de phrases complètes. La
difficulté, dans ce cas, est d'avoir des listes exhaustives, de
mémoriser ces listes, de les mettre à jour et de les interroger très
rapidement.

Les correcteurs utilisés dans les applications sont des correcteurs
orthographiques simples. Parfois, ils font des corrections liées à des
règles grammaticales mais il est difficile de savoir exactement
quelles corrections ils sont capables de faire. Par conséquent, **en
pratique**, lorsque vous avez rédigé un texte, vous faites passer un
correcteur orthographique, vous corrigez les erreurs si il y a lieu, puis
vous revérifiez l'orthographe par un humain en se concentrant sur les
possibles fautes grammaticales restantes.

### Le navigateur affiche une page Web

Le navigateur est devenu une application très complexe car il est
l'interface privilégiée d'interaction avec les utilisateurs dans le
monde numérique. Nous nous limitons ici à une fonctionnalité :
afficher un document `html` auquel est associé une feuille de style et
des images. Ce programme est en réalité très complexe mais nous en
présentons ici une vue abstraite pour aider à la compréhension. En
particulier, nous allons considérer que les programmes s'exécutent
l'un après l'autre alors que tous les programmes s'exécutent en
parallèle en interaction les uns avec les autres. En effet, vous avez
constaté que lors de l'affichage d'une page Web, certaines parties ou
certains éléments sont affichés alors que le navigateur est en attente
d'autres ressources.

Le navigateur lit le document `html` qui est un texte, c'est-à-dire
une suite de caractères. Ce texte contient des caractères particuliers
qui définissent des balises. Un premier programme qui connaît le
langage `html` va interpréter ce texte et construire un arbre qui
correspond à la structure du document : une entête et un corps, le
corps qui contient des sections, chaque section qui peut contenir un
titre, des sections, des listes, ... Les éléments de base seront des
balises comme une balise hyperlien, une balise image, et des portions
de texte. Certaines balises contiennent des liens vers des ressources
comme la feuille de style ou des images. Des programmes sont lancés
pour chercher ces ressources.

Nous pouvons donc supposer que le navigateur a lancé des programmes
qui ont construit l'arbre représentant le fichier source et permis de
récupérer la feuille de style et les images. Sans feuille de style, le
navigateur ferait un affichage par défaut sur fond blanc avec des
styles par défaut pour le titre, les sections et leurs titres, les
listes, le haut de page, le bas de page, ..., et bien sur les contenus
textuels. Cet affichage va être modifié par la feuille de style en
utilisant l'arbre représentant le document. Tout d'abord, un style
général va être appliqué à la boîte qui va contenir la page
affichée. Ce style précise le fond (sa couleur ou une ou plusieurs
images), les marges (en haut, en bas, à gauche, à droite), la police
de caractère, la taille des caractères, ... Ensuite, on applique un
style pour le titre, c'est-à-dire à la boîte qui contient le titre,
avec encore le fond, les marges, les propriétés des caractères. On
applique un style aux sections, c'est-à-dire à toutes les boîtes qui
vont contenir des sections, puis le style aux boîtes à l'intérieur des
sections comme, par exemple, une boîte contenant une liste ordonnée,
puis un style pour les items de la liste ... La page est alors
affichée avec sa structure, la présentation visuelle définie par la
feuille de style, le contenu textuel et les images.

Beaucoup d'éléments un peu complexes ont été oubliés dans la
description précédente comme le calcul de la taille des boîtes, la
taille des images et leur positionnement, l'adaptation à la taille de
l'écran (noter qu'il existe des moyens de définir des styles adaptés
au support de lecture et à la taille de l'écran), le positionnement
relatif de tous les éléments, ... Cependant, la compréhension des
principes généraux de ce programme doivent vous aider à concevoir des
pages Web même si vous utilisez des outils de type `WYSIWYG`,
c'est-à-dire des outils de conception guidés par le rendu. En
particulier, avoir bien compris la structure d'arbre d'un document
`html` est éclairant, par exemple, pour concevoir des feuilles de
style avec le principe  de boîtes emboitées les unes dans
les autres qui correspondent à la structure d'arbre du document `html`.

### Un jeu d'échec sur ordinateur

Le jeu d'échecs est un jeu ancien datant du 10ème siècle
environ. C'est un jeu de plateau, c'est-à-dire un jeu qui se joue avec
des pièces positionnées sur un plateau découpé en cases. Le plateau du
jeu d'échecs est un plateau de 64 cases de forme carrée avec des cases
blanches et des cases noires. C'est un jeu à deux joueurs. Chacun des
joueurs dispose de 16 pièces de différente nature : les pions, les
tours, ..., le roi et la reine. Chacune des pièces a des possibilités
de déplacement et des possibilités de prise de pièce adverse. Le jeu
est défini par un ensemble de règles très précises pour les
déplacements, les prises, le calcul du gagnant.

Nous nous intéressons à la question de faire jouer un ordinateur au
jeu d'échecs. La réalisation d'un programme de jeu capable de gagner
contre les humains a été un sujet important de l'intelligence
artificielle sur toute la seconde moitié du 20ème siècle. Il a fallu
attendre 1997 pour qu'un ordinateur puisse gagner contre le meilleur
joueur humain, en l'occurence le programme "Deep Blue" qui gagne
contre Kasparov en `1997`. Désormais, des programmes, qui peuvent être
exécutés sur un ordinateur personnel, sont plus forts que tout expert
humain. Nous allons expliquer les principes algorithmiques qui font
"l'intelligence" de ces programmes.

Nous laissons complètement de côté toutes les questions liées au
graphisme, aux interactions entre le joueur humain et le
programme. Nous supposons que le programme dispose d'une
représentation numérique du plateau et des pièces, qu'il existe des
programmes permettant de vérifier qu'un déplacement est autorisé,
permettant de calculer, pour un état du jeu, tous les déplacements
possibles du joueur qui doit jouer, permettant de voir si la partie
est finie et de déclarer le match nul ou le gagnant. Nous nous
intéressons donc simplement à la question suivante : la partie étant
dans un certain état après plusieurs coups de chacun des deux joueurs,
comment le programme peut-il choisir le meilleur coup à jouer ?

Si vous avez déja joué à un jeu de plateau, vous raisonnez très
certainement de la façon suivante : quels sont les coups possibles ?
Pour chacun d'eux, voir leur effet, réfléchir à la réponse potentielle
de mon adversaire, de penser à ce que je pourrais jouer ensuite,
... Après avoir examiné un certain nombre de coups possibles, je fais
un choix. Un algorithme va avoir une approche similaire mais très
systématique. Il va considérer tous les coups possibles de sa part,
tous les coups possibles de l'adversaire, tous les coups possibles de
sa part, ... L'objet informatique construit est un arbre : la racine
est l'état courant du jeu, les fils sont les états du jeu pour chaque
coup possible, etc. Une première idée est donc de construire cet arbre
de toutes les suites possibles du jeu à partir de l'état courant,
calculer le coup qui m'amène le plus souvent dans une situation
gagnante et le choisir.

Le problème est-il résolu ? Malheureusement non ! Nous avons signalé,
dans l'introduction de ce module, la notion d'être calculable par une
machine. Mais il ne suffit pas qu'un problème soit calculable. Il faut
qu'il le soit avec une mémoire et un temps de calcul raisonnables. Sur
notre exemple, imaginez qu'il y ait environ 10 coups possibles et
qu'on souhaite regarder les états possible pour 10 tours de jeu, soit
pour 20 coups. Il y aurait 10 puissance 20 états possibles, soit
encore 1 suivi de 20 zéros, soit encore 100 milliards de milliards
d'états possibles. Il est **impossible** à toute machine de mémoriser
ces états ou de faire des calculs sur tous ces états. C'est ici qu'il
faut donc être "intelligent" pour notre programme.

Vu que le programme ne peut pas explorer le jeu pour voir si un coup
mène sur une position gagnante, nous allons doter le programme d'une
fonction d'évaluation d'un état du jeu. Dans sa forme la plus simple,
une valeur est attribuée à chacune des pièces et l'évaluation d'un
état du jeu consiste à sommer la valeur des pièces dont le joueur
dispose dans cet état. Cette fonction peut être améliorée par des
bonus ou malus dépendant de la position de la pièce. Par exemple, on
va bonifier un pion qui est près du camp adverse car il peut se
transformer en reine, on va pénaliser un pion isolé car il peut être
pris facilement. Nous supposons qu'une fonction d'évaluation a été
choisie.

Faisons le point. Le jeu est dans un certain état (une configuration
du jeu après plusieurs coups), le programme doit choisir un meilleur
coup à jouer. La succession des coups que chacun des joueurs peut
jouer définit un arbre de tous les états possibles. Nous savons qu'il
est impossible d'explorer cet arbre complètement. L'idée de base de
l'algorithme est de l'explorer incomplètement mais
intelligemment. Pour cela, on utilise la fonction d'évaluation pour
attribuer un score à un état de l'arbre. En effet, on va explorer
l'arbre en éliminant complètement des sous-arbres lorsqu'on estime que
les scores dans ce sous-arbre ne seront pas assez bons.  C'est un peu
ce qu'un joueur humain fait : si je joue ce coup, je perd ma reine et,
sauf cas particulier, ce coup n'est pas intéressant donc je ne vais
pas explorer plus loin ce qui peut se passer. C'est ce principe qui a
été formalisé bien plus précisémment en utilisant les scores sous
forme d'un algorithme célèbre appelé *algorithme alpha-beta*. 

Vous connaissez maintenant les principes du fonctionnement de
l'algorithme. Pour avoir un algorithme performant on examinera le plus
grand nombre d'états possibles dans l'arbre simplifié grace à la
méthode alpha-beta. Pour avoir un algorithme très performant, on
ajoute d'autres éléments comme, par exemple, une bibliothèque des
débuts de partie. C'est-à-dire que le programme pourra mimer des
débuts de partie classiques des meilleurs joueurs qui sont connues sur
quelques coups en début de partie. Mais avoir le jeu le plus fort ne
sera pas le seul critère car un joueur standard n'a pas le niveau du
champion du monde et ne prendra pas plaisir à perdre toutes les
parties qu'il joue ! Avoir un jeu qui s'adapte à l'utilisateur est une
question importante qui est toujours étudiée par les concepteurs de
jeux.

Il est difficile de ne pas parler du jeu de Go qui défraie la
chronique au moment de la rédaction de ce cours en 2016. En effet,
pour la première fois, un programme gagne contre le champion du monde
du Go alors qu'on croyait le Go hors de portée des machines. En effet,
le nombre de configurations du Go est encore plus gigantesque que pour
les échecs et les stratégies des joueurs utilisent une vue spatiale de
l'état du jeu qu'on pensait réservée au cerveau humain. Le programme
de Go utilise des techniques d'apprentissage automatique ("machine
learning" en anglais) avec un programme de jeu qui s'améliore avec
l'expérience, c'est-à-dire qu'il "apprend" à partir de parties jouées
(contre un humain ou contre lui-même). Un petit cocorico Lillois (les
rédacteurs de ce cours sont Lillois) car c'est notre collègue Rémi
Coulom qui a initié ces recherches sur le Go avec un programme
champion du monde dans les années 2010, battant même des experts
humains mais avec handicap.

```compréhension
::Représenter et manipuler::
[markdown]
**Représenter et manipuler**
Les traitements possibles dépendent fortement des choix de représentation
{T}
```

# Optionnel -- Représentation des données

Nous avons introduit des notions d'algorithmique et de conception
d'applicationsmais ceux-ci doivent manipuler des données. Il faut donc
également considérer les données manipulées et les choix de
représentation de ces données. En effet, si nous avons signalé les
contraintes d'efficacité, nous ne les avons pas prises en
compte. L'efficacité d'un programme est lié au choix de l'algorithme
mais aussi au choix de la représentation des données. Nos applications
doivent traiter des objets divers comme des nombres et des chaînes de
caractères mais aussi des documents, des images, des tableaux,
... Nous allons, dans cette section, étudier comment sont définies des
données complexes à partir de données élémentaires et voir que les
choix d'organisation peuvent être nombreux et influent sur les
performances d'une application. Avant cela, une parenthèse sur la
façon dont on mémorise les données dans les applications avec la
notion de **variable informatique**.

Les applications manipulent des caractères, des nombres, des listes,
des documents, des images. Ces objets doivent pouvoir être mémorisés
dans la mémoire de la machine et on doit pouvoir les retrouver au
besoin. La gestion de la mémoire étant complexe, on utilise un
mécanisme de **nommage avec des variables**. Supposons que
l'application ait besoin de manipuler un caractère, on peut utiliser
une variable `caracourant` dans laquelle on va pouvoir mémoriser un
caractère et avec laquelle je pourrais retrouver le caractère
mémorisé. On peut, de même, utiliser une variable `note` pour un
nombre entre 0 et 20, ou encore une variable `montexte` pour une suite
de caractères. On peut aussi considérer une variable `listenotes` pour
gérer une liste de notes. Le principe est que, lorsqu'une variable est
définie, la machine range la valeur (qui peut être complexe) à une
adresse dans la mémoire et que la machine saura retrouver la valeur
car elle mémorise l'association entre le nom de la variable et
l'adresse mémoire. Illustrons ceci sur un exemple de programme simple

`TRAIT2NOTES`

1. `nbnotes` <- 2
2. saisir une note au clavier et ranger la valeur dans `note1`
3. saisir une note au clavier et ranger la valeur dans `note2`
4. afficher le message "la plus petite note est : ", afficher le
   résultat du calcul `MIN(note1,note2)`
5. afficher le message "la moyenne est : ", afficher le résultat du
   calcul `(note1 + note2)/nbnotes`

La première instruction est une *affectation* : on range la valeur 2
dans la variable `nbnotes`. Les instructions 2 et 3 sont une
affectation à partir d'une interaction avec l'utilisateur du programme
qui choisit une première valeur rangée dans `note1` puis une seconde
valeur rangée dans `note1`. L'instruction 4 correspond à l'affichage
d'un message et du résultat du calcul du minimum des 2 valeurs qui
viennent d'être rangées dans `note1` et `note2`. Les variables
permettent donc de désigner des objets par un nom pour ranger et
retrouver des valeurs sans que l'utilisateur ait à gérer la complexité
des accès à la mémoire de la machine. Il faut noter que le concepteur
du programme utilise des variables pour expliquer à la machine ce
qu'elle doit faire. Par contre, l'utilisateur ne voit pas les
variables. Par exemple, l'utilisateur de notre programme saisit une
première valeur, par exemple 12, puis une seconde valeur, par exemple
14, et tout ce qu'il verra sont les résultats produits, soit sur notre
exemple, "la plus petite note est : 12", "la moyenne est : 13"

### Types de données élémentaires

Nous avons auparavant introduit que nous pouvions étendre les
capacités de notre machine. En particulier, nous avons vu qu'à partir
de simples 0 et 1, on pouvait définir des nombres entiers et on
pouvait définir des caractères en utilisant des codages adéquats. Ceci
peut être généralisé et nous allons étudier les données élémentaires
que peut utiliser une machine.

On peut utiliser des **nombres ou valeurs
numériques**. Les choix sont divers et diffèrent selon les
environnements. On distingue souvent les nombres entiers avec le type
`entier` ou `integer`. Ils peuvent être codés sur 1, 2, 4, ou un
nombre quelconque d'octets ce qui permet de représenter des ensembles
plus ou moins grands d'entiers. Par exemple, sur 1 octet on peut coder
256 valeurs soit les entiers de 0 à 255 si on se limite à utiliser des
entiers positifs, soit les entiers de -128 à +127 sinon. Sur 2 octets,
on peut coder 65 536 entiers. Pour les nombres avec une partie
décimale, on définit le type `décimal` ou `réel`. On peut ici encore
avoir des codages plus ou moins longs qui donnent une précision plus
ou moins importante. Pour des calculs scientifiques ou des calculs
financiers, on utilise des nombres avec une très grande précision. Que
ce soit pour les entiers ou les réels, on dispose de beaucoup de
fonctions permettant de mettre en oeuvre de nombreux calculs.

Ensuite, il existe un type pour manipuler les valeurs de vérité que sont
`VRAI` et `FAUX`, c'est le type **Booléen** ou **Boolean**. Il est
très utilisé en informatique car il correspond aux valeurs que peut
prendre une condition et ces conditions sont utilisées dans
l'alternative (le si alors sinon) et l'itérative (le tant que). On
dispose d'opérations comme le `NON`, le `ET` et le `OU`. On notera que
le `OU` logique est dit inclusif, c'est à dire qu'il vaut `VRAI` si l'un
des deux ou les deux valent `VRAI`. Par exemple, `être-grand OU
être-blond` vaut `VRAI` si je suis grand ou blond ou un grand
blond. Dans la langue française, on utilise le ou comme conjonction de
coordination avec un sens qui peut être inclusif ou exclusif selon les
expressions. Les valeurs de vérité et la logique sont utiles également
pour modéliser le raisonnement comme en intelligence artificielle mais
nous en parlerons dans un autre cours.

### Types de données structurés

On peut assembler des données élémentaires pour construire des données
structurées. Par exemple, on peut construire des tableaux de
nombres. Un tableau de nombres à une dimension contient des nombres et
on peut accéder à chaque nombre du tableau par son indice. On aura le
premier nombre du tableau, le second, le dernier, ... Un tableau à
deux dimensions sera organisé en lignes et en colonnes, il y aura deux
indices et on pourra accéder au nombre situé en ligne `i` et en
colonne `j` du tableau. Ces structures de données sont très utiles dès
que l'on fait des calculs qu'ils soient scientifiques, économiques ou
financiers. Il existe bien d'autres structures de données qui se
distinguent les une des autres par la façon d'organiser les données,
de pouvoir accéder aux données, de pouvoir les parcourir. Chacune des
structures peut être mieux adaptée qu'une autre en fonction des
besoins et des performances attendues. Plutôt que de parcourir toutes
ces structures, nous allons considérer les documents textuels et voir
l'importance de la structure pour les traitements à réaliser.

Un document peut être représenté par une **chaîne de caractères**. En
règle générale, une chaîne de caractères est une suite de caractères
indicée de 1 à un indice qui est la longueur de la chaîne (parfois on
commence à compter à 0) ce qui permet de parler du premier caractère,
du second caractère, du dernier caractère. Nous avons vu dans une
précédente section comment on pouvait définir des fonctionnalités sur
les chaînes de caractères. On dispose souvent d'un grand nombre de
fonctions comme transformer en majuscules, extraire les premiers
caractères, compter le nombre d'apparitions d'un caractère, parcourir
tous les caractères. Cette représentation correspond à une *structure
séquentielle* dont nous allons voir les possibilités. 

Considérons une application comme un éditeur de textes ou un
traitement de textes déja considérée dans le cours sur les
documents. Regardons comment peut-on chercher un mot dans un
texte. Par exemple, cherchons le mot `taille` dans le texte du cours
de la section 3 du cours sur les traitements. Un programme de
recherche va, en gnéral, fonctionner comme suit : il prend une fenêtre
de longueur 6 (le mot cherché est de longueur 6) se positionne sur le
premier caractère du texte, teste si la fenêtre contient le mot
`taille`, si oui il positionne un curseur ou met en couleur le mot
trouvé, si non il passe à la deuxième position et recommence jusqu'à
avoir trouvé le mot ou être arrivé à la fin du document. C'est un
*traitement séquentiel* et le programme doit parcourir tout le
document. Peut-on faire mieux ? Nous verrons une réponse positive à
cette question dans le cours sur la recherche d'information.

Considérons maintenant le cas où le document possède une
structure. C'est, par exemple, le cas pour un document `html` qui est
un document textuel avec une structure définie à l'aide de
balises. Une application, comme le navigateur, peut alors représenter
le document avec une *structure arborescente* : la racine du document
qui contient une entête ("head") et un corps ("body"), le corps
contient un titre et des sections, les sections peuvent contenir des
sections contenant des paragraphes et des listes. Quel avantage
apporte cette structure en forme d'arbre ? Par exemple, l'application
peut accéder directement au titre sans parcourir le document,
l'application peut numéroter facilement les sections ou construire une
table de navigation sans parcourir tout le document. Le navigateur
peut appliquer les styles en fonction de cette structure : il applique
le style de la page (fond, marges, retraits), puis les styles de
section, puis les styles des titres de section, ... Qu'en est-il de
notre programme de recherche d'un mot dans la page Web ? On utilise le
même programme que précédemment pour les contenus textuels aux
feuilles de l'arbre. La structure arborescente facilite et accélère
les traitements pour le navigateur. La conscience de cette structure
pour un utilisateur permet de bien comprendre ce qu'est une page Web
et permet de définir des styles appropriés si vous êtes amenés à
modifier l'apparence de pages Web.

### Les objets

```compréhension
::Représenter et manipuler::
[markdown]
**Représenter et manipuler**
Les traitements possibles dépendent fortement des choix de représentation
{T}
```

[^1]: Faut-il citer des sociétés ?