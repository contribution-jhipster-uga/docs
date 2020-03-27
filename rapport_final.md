# Rapport Final
## Sujet
Le sujet traité par notre équipe dans le cadre de ces projets à été "Contribution open-source au projet JHipster". Ce projet à consister à la réalisation de divers modules venant enrichir la bibliothèque de module du générateur JHipster afin de les inclure dans le marketplace du projet.
## Technologies employées
Les projets générés par JHipster utilisent tout un ensemble de technologies qu'il nous a fallu travaillé afin de parvenir à efficacement concevoir de nouveaux modules. Ainsi nous avons dû nous interesser à divers langages et framework tel qu'**Angular** et **Spring**, mais aussi **TypeScript**, **HTML**, **CSS**.

Nous avons également travaillé avec un ensemble d'outils et de bibliothèque préexistante pour la conception de nos modules tel qu'**ApacheTika**, **Tesseract** et **ImageAI** pour nos modules d'indexations, ainsi que **FullCalendar** et **ical4j**.

Nos modules étant principalement développé en **Javascript**, nous avons également beaucoup travaillé avec **Node.js**.

Nous avons enfin utilisé **Git** pour le versionning de tous nos developpements, ainsi que les outils **Trello** et **Discord** pour la gestion de notre projet et notre communication interne.
## Réalisations techniques
### [Module Cache](https://www.jhipster.tech/modules/marketplace/#/details/generator-jhipster-imageblobcache)
Ce module permet d'utiliser des **ImageBlob** stockés en base de données avec un **système de cache**.
En effet, l'appel d'une image dans une base de données représente une transaction de grande quantité de données à chaque fois qu'on a besoin d'une image. Le système de cache va permettre de réduire le nombre d'appels à la base de données.
Si une image est affichée plusieurs fois dans un intervalle de temps réduit (1h), on demande au navigateur de vérifier s'il ne possède pas l'image dans son cache afin de ne pas réitérer l'appel à la base de données. L'image sera alors directement affichée sans transaction d'une grande quantité de données depuis la base de données.

L'entité **Photo** qui représente une ImageBlob comporte l'image au moment de la sauvegarde en base de données. Cependant lorsque le cache intervient, on veut que la base de données ne fasse pas appel aux octets correspondant à l'image. On a alors fait le choix de passer par une autre entité **PhotoLite** qui récupère les informations associées à une image (titre, notes, full-text indexation data, etc) mais sans les octets de l'image (cf schéma ci-dessous).

### [Module Indexation](https://www.jhipster.tech/modules/marketplace/#/details/generator-jhipster-imageblobindexation)

Ce module permet d'ajouter des images dans une base de données et de les visualiser à l'aide d'un système de cache (voir ci-dessus). Ce module permet également l'indexation de ces images à l'aide de l'outil **Elasticsearch**. 
Lors de l'upload d'une image, cette dernière est traitée à l'aide des bibliothèques :
- **ApacheTika** : Pour l'extraction des métadonnées liées à l'image
- **Tesseract** : Pour l'extraction des textes dans une image
- **ImageAI** : Pour la détection et la prédiction des objets dans une image

L'indexation par **Elasticsearch** se base sur le titre, les notes et les différents champs correspondant au traitement. Une barre de recherche est disponible dans l'entité photo pour utiliser cette indexation.

Les principales métadonnées extraites par **ApacheTika** sont : 
- L'extension de l'image
- Les dimensions de l'image
- La compression utilisée
- L'espace colorimétrique utilisé (Y, Cb, Cr)

**Tesseract** s'appuie sur les données de [Tessdata](https://github.com/tesseract-ocr/tessdata) pour permettre l'extraction de texte, à partir d'une image, dans une langue spécifique. Pour le moment, le module utilise uniquement le fichier **eng.traineddata**, ce qui signifie que seule l'extraction anglaise est possible.

**ImageAI** permet de détecter et de prédire les objets présents dans une image. Cette bibliothèque s'appuie sur l'utilisation de différents réseaux de neurones permettant d'ajuster le rapport temps/précision. Ce module utilise les réseaux de neurones Resnet qui sont précis, mais qui nécessite un certain temps d'exécution.

### [Module Fullcalendar](https://www.jhipster.tech/modules/marketplace/#/details/generator-jhipster-fullcalendar)
Module permettant l'ajout des dépendances necessaire à l'utilisation et la gestion des outils **FullCalendar**. Cet outil permet à son utilisateur d'accéder à tout un ensemble de fonctionnalité liée à la gestion des calendriers tels que la création de nouveaux calendriers, de nouveaux événements ainsi qu'à leur visualisation dans un calendrier personnalisable. Plus d'information sur [la page officielle](https://fullcalendar.io/docs/angular). 
### [Module Ngx-Charts](https://www.jhipster.tech/modules/marketplace/#/details/generator-jhipster-ngx-charts)
Ce module permet d'utiliser la librairie **Ngx-Charts** dans un projet Jhipster et notamment les **Simple Entry, Multiple Entry et Bubble Chart**. De plus, on a ajouté dans le backend le système permettant de récupérer les données en base de données et de les formatter de façon à qu'ils puissent être directement utilisées par les différents Charts. 

Pour ce faire, les résultats des requêtes provenant de la base de données sont transformés (projection) et convertis pour donner un DTO correspondant au bon chart. 
## Architectures techniques
L'architecture d'un module Jhipster se présente comme ceci:

![](https://i.imgur.com/QKcs6eL.png)

Le répertoire __templates/__ contient les fichers qui sont nécessaire à l'installation du module sur un projet Jhipster. L'organisation des fichiers est décider par le développeur, dans notre cas elle mimique l'architecture d'un projet Jhipster pour faciliter la compréhension du module.
Le répertoire __test/__ contient les fichers qui sont nécessaire à l'installation de la partie test du module sur un projet Jhipster. Comme pour la partie __templates/__ l'organisation mimique l'architecture d'un projet Jhipster pour faciliter la compréhension du module.
Le fichier __index.js__ contient les instructions à réaliser lors de l'installation du module. C'est ici que l'on spécifie: les fichier qui doivent être copié, les dépendances à ajouter, les modifications sur certains fichers, etc.
Le fichier __package.json__ contient les informations nécessaires à l'utilisation du module en tant que package npm. On y trouve notamment le nom du package, le numéro de version, une description, les dépendances, etc.
Le fichier __package-lock.json__: est généré lorsque vous apportez des modifications dans le fichier "package.json" ou dans node_modules. Ce fichier stocke la structure des dépendances à chaque installation.
Le fichier __yo.rc.json__ contient les configurations de plusieurs générateurs.

### Module Cache
![](https://i.imgur.com/I8TZdDz.png)

### Module Fullcalendar
![fullCalendar Architecture](https://i.imgur.com/L3Sv0hl.png)
### Module Ngx-Charts
![Ngx-Chart module Architecture](https://i.imgur.com/dxgdeqM.png)

## Gestion de projet
Afin d'organiser au mieux le temps imparti pour mener à bien ce projet, deux rôles ont été attribués à des étudiants du projet : Alexis Lattard à été nommé chef de projet et Tom Solvery Scrum Master. Leurs rôles leurs ont donné à charge de gérer certains aspects managériaux et organisationnels du projet. 

Tout d'abord, des réunions quotidiennes ont été mises en places afin de favoriser la communication au sein du groupe, 5 minutes seulement chaque matins afin que chacun puisse exposer au groupe les difficultés rencontrées et leurs objectifs à court terme. 

Chaque semaines nous avions également une réunion qui s'organisait avec avec notre tuteur de projet Mr Donsez. Cette réunion permettait de mettre en avant la progression de nos objectifs et de discuter de la meilleur façon de continuer a faire avancer le projet.

En parallèles de ces réunions, nous organisions également une réunion entre nous afin de discuter des objectifs de chacun pour la semaine à venir et ainsi mettre en place un programme adapté à chacun lui permettant de faire avancer correctement ses objectifs.

## Métriques logiciels

### Module ImageBlob Indexation et cache
Le total de commits sur le projet est de 250  (30% Thibaut, 30% Maxime, 30% Tom, 10% Alexis)
Le nombre de ligne de code du module est de 2800.
Les langages utilisés sont Java, Javascript, HTML, XML et Python
D'après le [COCOMO II](http://groups.umd.umich.edu/cis/course.des/cis525/js/f00/kutcher/kutcher.html) :
L'effort estimé est de 7 personnes/mois.
La durée estimé est de 5 mois.
Soit 2 personnes suffisent pour le module.

### Module Ngx-Charts
Le total de commits sur le projet est de 30  (100% Tom)
Le nombre de ligne de code du module est de 1600.
Les langages utilisés sont Java, Javascript, HTML, XML et SASS
D'après le [COCOMO II](http://groups.umd.umich.edu/cis/course.des/cis525/js/f00/kutcher/kutcher.html) :
L'effort estimé est de 4 personnes/mois.
La durée estimé est de 4 mois.
Soit 1 personne suffit pour le module.

### Module FullCalendar
Le total de commits sur le projet est de 220  (50% Ergi, 35% Corentin, 15% Alexis)
Le nombre de ligne de code du module est de 6800.
Les langages utilisés sont Java, Typescript, Javascript, HTML et XML
D'après le [COCOMO II](http://groups.umd.umich.edu/cis/course.des/cis525/js/f00/kutcher/kutcher.html) :
L'effort estimé est de 18 personnes/mois.
La durée estimé est de 7 mois.
Soit 2-3 personnes suffisent pour le module.


## Conclusion
Le bilan de ce projet est pour nous très positif car il nous a permis de découvrir les aspects communautaires de la programmation. Avoir pu contribué à un projet open-source tel que JHipster nous a permis de nous rendre compte de l’importance de l’entraide dans la communauté informatique et que chacun d’entre nous pouvait avoir sa pierre à apporter à l’édifice de son choix tant les projets sont multiples en lignes.

Nous avons donc eux l’occasion d’apporter au projets JHipster 4 nouveaux générateurs qui pourront être réutilisé par les utilisateur du projet. Ces générateurs permettent d’inclure dans un projet JHipster de nouvelles fonctionnalitées très varié : La génération d’un système de cache permettant la fluidification de l’utilisation du projet, un système d’indexation automatiques des données d’images importées, un système de calendrier partagée, ainsi qu’un ensemble d’outils permettant la créations et l’exploitation de graphiques. Toute cette variété a permis à l’équipe de découvrir des aspects très différent les uns des autres de ce projet.

Toute l’équipe a ainsi pu monter en compétences dans un ensemble de domaines très varié, autant au niveau de la programmation et des technologies web utilisé que dans la connaissance du fonctionnement d’une équipe. Nous avons également tous pu travailler nos compétences en matière de communications et de gestions de projets. Toute ces compétences seront sans nul doute utiles à chacun d’entre nous à l’avenir et leur mise en pratiques nous aura permis de poser sur tout cet ensemble un regard nouveau.

## Glossaire
**JHipster** : Générateur d'application libre et open source utilisé pour développer rapidement des applications Web modernes en utilisant Angular et le framework Spring

**Code open-source** : Libre de redistribution, d'accès au code source et de création de travaux dérivés. Mis à la disposition du grand public, ce code source est généralement le résultat d'une collaboration entre programmeurs.

**Yeoman** :  Pile de développement open source côté client, fournissant des outils et des frameworks pour permettre le développement rapide d'application webs.

**npm** : Gestionnaire de paquets officiel de Node.js, npm fonctionne avec un terminal et gère les dépendances pour une application.

**COCOMO II** : Modèle permettant de définir une estimation de l'effort à fournir dans un développement logiciel et la durée que ce dernier prendra en fonction des ressources allouées. Le résultat de ce modèle n'est qu'une estimation, il n'est en rien infaillible ou parfaitement exact.

## Dépôt Git des modules 

- [ImageBlob Indexation with cache control ](https://github.com/contribution-jhipster-uga/generator-jhipster-indexation-imageblobcache)
- [ImageBlob cache control](https://github.com/contribution-jhipster-uga/generator-jhipster-imageblobcache)
- [Ngx-Charts](https://github.com/contribution-jhipster-uga/generator-jhipster-ngx-charts)
- [FullCalendar](https://github.com/contribution-jhipster-uga/generator-jhipster-fullcalendar)
## Webographie
https://www.jhipster.tech/
https://imageai.readthedocs.io/en/latest/
https://swimlane.gitbook.io/ngx-charts/
https://www.elastic.co/fr/
https://tika.apache.org/
https://github.com/tesseract-ocr/tesseract
https://spring.io/projects/spring-boot
https://fullcalendar.io/
https://github.com/ical4j/ical4j

