# Fiche de suivie

## 29/01 : 
Etablissement des rôles au sein de l’équipe
Lecture de la documentation “Création d’un module Jhipster” 
Génération d’un premier module “Test”


## 31/01 :
Génération d’un projet JHipster LazyBlob.
Analyse des modules créés l’année précédente (ChatBot Rasa - Stripe).
Correction du module ChatBot Rasa.
Identification des problèmes présents sur Stripe.
Test du module ImageIA (Réseau de neurones ResNet)

## 03/02 :
Rendez-vous avec Didier Donsez pour établir le cahier des charges.
Préparation des Sprints (Backlog)

## 04/02 : 
Mise en commun des tâches à faire, répartition du backlog.
Ergi + Corentin : JSON-LD bloqué, envoie d’un message à Didier Donsez pour nous débloquer. Début FullCalendar et prise en main d’Angular.
Maxime : Génération des variables associées au type ImageBlob
Alexis + Thibaut + Tom : Indexation Full-Text ImageAI, OCR, Apache Tika

Développement d’une fonction de détection d’image avec ImageAI (Python + Intégration à Spring)
Développement d’une fonction de parsing metadata avec Apache Tika


## 05/02 : 
Ergi + Corentin : Prise en main d’Angular et mise en place + configuration de l’API FullCalendar sur JHipster
Maxime : Ajouts des fichiers nécessaires au module.
Alexis + Thibaut + Tom : Intégration des fonctions du module d’indexation dans une classe java Indexation. 
Traitement d’une image lors d’un ajout en BDD pour compléter les champs extractedObject, exif à l’aide des fonctions d’Indexation.

## 07/02 :
Alexis + Thibaut + Tom : Correction des fonctions d’indexation afin qu’elle fonctionne sous linux. -> Succès
Maxime : Ajouts des fichiers “changelogs” pour la mise en place des entitées dans la base de données.

Corentin : AFK the morning

Ergi : Récupération des events de la base des données pour les afficher dans fullCalendar.

## 10/02 :
Rencontre avec Didier Donsez. Discussion autour du @Lazy et de la suite du projet LazyBlob.
Créer de nouveau DTOs (L’un avec tous les champs, un autre avec @Lazy)
Créer un service pour récupérer la ressource Lazy en question.

Maxime: modification des imports et package dans les fichier .java pour qu’ils respecte l’architecture du projet jhipster dans lequel le module est installé.

Ergi: Créer un nouveau event avec fullCalendar et l’ajouter dans la base de données.
 
## 11/02 :
Ergi + Corentin : Génération d’un nouveau projet avec le modèle complète.
Alexis + Thibaut + Tom : On a étudié le code du projet Lazyblob qui gère l’appel des images avec gestion du cache.

Maxime : Absence justifiée

## 12/02 : 
Alexis + Thibaut + Tom : Application et test de la route GetBlobImage à plusieurs endroits de l’application.

Maxime: modification des imports et package dans les fichier .java pour qu’ils respecte l’architecture du projet jhipster dans lequel le module est installé.
Ergi : Finalisation d'une page web de base pour travailler avec fullCalendar.
13/02 :
Alexis + Thibaut + Tom : Correction d’erreur sur le récupération des données liées à l’api.
Corentin : Travail sur la partie modal.
Ergi: Gestion de la visibilité des événements selon leur aspect privé et leur créateur.
Maxime: Ajout de la contrainte ManyToOne entre l’entité photo et l’entité user.

## 14/02 :
Alexis + Thibaut + Tom : Continuation des corrections d’erreur, et réalisaiton des tests avec l’outil d’indexation Elasticsearch.
Corentin : Travail sur la partie modal.
Ergi: Gestion de la visibilité des événements selon leur aspect privé et leur créateur.
Maxime : Correction d’une incohérence au niveau d’un champ dans l’entité photo (le champ update_at ---> updated_at)

## 18/02 :
Réunion avec Didier Donsez.
Alexis + Thibaut + Tom : Création d’une nouvelle entité PhotoLite pour permettre un appel Lazy au niveau du JPARepository.
Corentin : Travail sur la partie modal.
Ajout du PhotoLiteRepository et du PhotoLiteMapper, modification des services et de la fonction getBlobasResponseEntity pour optimiser l’appel des images. 

Maxime: Ajout du Front-end dans le module.
Ergi: Gestion de l'internationalisation du calendrier.


## 20/02 :
Alexis : Diaporama soutenance intermédiaire
Thibaut + Tom : Adaptation du front end avec PhotoLite pour permettre l’utilisation du cache du navigateur pour le chargement de la liste de photos.
Corentin : Correction des bugs du modal.
Maxime: Ajout du Front-end dans le module.
Ergi: Bug de l'internationalisation, recherche des moyens de résolution.
## 21/02 :
Thibaut : Modification des query Elasticsearch, pour permettre l’indexation sur le titre, la note, la détection d’objet, l’extraction de textes, les métadonnées.
Tom : Modification de la fonction du cache-control afin qu’elle fonctionne avec l’entité PhotoLite
Corentin : Correction des bugs du modal.
Alexis : Création de fake-data pour l’utilisation des calendars
Maxime: Ajout du Front-end dans le module.
Ergi: Bug de l'internationalisation, problème courant avec fullCalendar. Ajout dans readme l’issue pour être suivi dans le futur.

## 02/03 :
Thibaut : Mise à jour du front avec les nouvelles requêtes via les repository Elasticsearch
Tom : Finalisation de l’implémentation de photoLite.
Corentin : Correction des bugs du modal.
Alexis : Ajout de boutons dans la page de calendars
Maxime: Ajout de la route du front au back.
Ergi: Améliorations visuelles du module, mise en page.

## 03/03 :
Thibaut : Intégration de la prédiction d’image à l’aide du réseau de neurones ResNet pour l’indexation full-texte.
Tom : Test de l’application exemple de Ngx-Charts afin d’intégrer un module Ngx-Charts.
Corentin : Intégration du modal avec la master.
Alexis : Ajout de fonctionnalités sur l’écran calendars
Maxime: Ajout des fichiers indexation/imageIA/.
Ergi: Améliorations techniques du module, conversion des objets events de notre bdd en objets plus optimisés pour le module.

## 04/03 :
Thibaut : Ajout dans le générateur du téléchargement automatique des réseaux de neurones lors de l’installation du module d’Indexation.
Tom : Intégration de la partie Bubble Charts dans le backend pour pouvoir utiliser les Bubble Charts dans le frontEnd.
Corentin : Review de code.
Maxime: Mise à jours des chemin des fichier dans indexation.java
Ergi: Début de prise en main de la librairie ical4j.

## 05/03 :
Thibaut : Finalisation et test du téléchargement automatique des réseaux de neurones.
Corentin : Recherche de documentation sur la création d’un générateur.
Tom : finalisation de la partie bubbleCharts côté front et back.
Alexis : Modification comportement des boutons
Maxime: Mise à jours des chemin des fichier dans indexation.java
Ergi: Début de prise en main de la librairie ical4j

## 06/03 :
Thibaut + Maxime: Fin des tests du modules pour une version sans Elasticsearch. Publication de cette version sur le marketplace de jHispter.
Tom : Modification de l’application exemple pour intégrer elasticSearch.
Corentin : Recherche de documentation sur la création d’un générateur.
Alexis : Modifications visuelles calendriers.
Ergi: Intégration de ical4j et ses dépendances dans un projet maven.

## 09/03 :
Thibaut + Maxime + Tom : Intégration des nouveaux fichiers liés à Elasticsearch dans le générateur du module d’Indexation.
Tom : Documentation sur la création d’un module et préparation du module Ngx-Charts
Corentin : Début de la création du générateur pour FullCalendar.
Ergi: Conflit entre les dépendances JHipster et celles de ical4j.

## 10/03 :
Thibaut + Maxime : Intégration des nouveaux fichiers liés à Elasticsearch dans le générateur du module d’Indexation. 
Tom : Début du développement du générateur Ngx-Charts.
Corentin : Création du générateur pour FullCalendar.
Ergi: Résolution du conflit. La librairie est connue et le projet compile.

## 11/03 :
Thibaut + Maxime: Publication d’une version du module avec Elasticsearch.
Corentin : Création du générateur pour FullCalendar.
Tom : Développement du module Ngx-Charts
Alexis : Préparation des documents finaux, soutenance et rapport
Ergi: ical4j export de l’agenda vers un fichier ics.

## 12/03 :
Thibaut : Bug fixe sur le générateur du module d’indexation.
Tom : Test, bug fix et publication du module Ngx-Charts
Corentin : Création du générateur pour FullCalendar.
Ergi: ical4j export de l’agenda vers un fichier ics fini.

## 13/03 :
Thibaut : Bug fixe sur le générateur du module d’indexation.
Tom : Développement d’une application avec exclusivement la gestion de cache pour ImageBlob
Corentin : Création du générateur pour FullCalendar.
Ergi: Restructuration de l’architecture des fichiers pour que le service ical4j soit mieux representé (fichiers ical.service.ts et ical.resource.java)

## 16/03 :
Thibaut : Tentative d’utilisation des HttpRequest pour le téléchargement des réseaux de neurones lors de l’installation du module et non plus via wget.
Tom : Développement du module ImageBlobCache
Corentin : Création du générateur pour FullCalendar.
Ergi: Difficulté de travailler face à la situation de pandémie Covid-19.

## 17/03 :
Thibaut : Finalisation des tests via l’HttpRequest, mais bug lors du téléchargement du fichier eng.traineddata, donc retour via wget.
Tom :  Test, bug fix et publication du module Imageblobcache sur le marketplace.
Corentin : Création du générateur pour FullCalendar.
Ergi: Difficulté de travailler face à la situation de pandémie Covid-19.

## 18/03 :
Thibaut : Test final du module d’Indexation pour la prise de capture d’ecran. Mise à jour du README.md à l’aide de ces captures.
Tom : Ajout des licences et mises à jour des dépendances sur le module Ngx-Charts et Cache.
Corentin : Création du générateur pour FullCalendar.
Ergi: Travail sur l’import d’un agenda à partir d’un fichier ics.

## 19/03 :
Thibaut : Mise à jour des liens vers les pré-requis pour le module d’Indexation, ajout de la license et ajout des TODO.
Tom : Mise en page du README.md du module Ngx-Charts et Cache
Corentin : Fin de création du générateur pour FullCalendar.
Ergi: Travail sur l’import d’un agenda à partir d’un fichier ics.

## 20/03 :
Thibaut : Ecriture du rapport final sur la partie dédiée au module d’Indexation.
Tom : Ecriture du rapport final sur la partie dédiée au module Ngx-Charts
Corentin : Début des tests du générateur appliqué à un nouveau projet.
Ergi: L’import d’un agenda à partir d’un fichier ics ok.

## 23/03 :
Thibaut : Ecriture du rapport final sur la partie dédiée au module d’Indexation.
Tom : Ecriture du rapport final sur l’architecture du module Ngx-Charts
Corentin : Poursuite des tests et du débug.
Ergi: Création d’un nouveau calendrier pour l’agenda importé

## 24/03 :
Corentin : Poursuite des tests et du débug.
Tom : Mise à jour de la liste des modules sur le Github Contribution JHipster UGA.

Maxime: Migration du module Indexation de Gitlab vers GitHub.
Ergi: Finalisation de la documentation sur fullCalendar et ical4j

## 25/03 :
Thibaut + Maxime : Enregistrement de la démonstration du module Indexation et Cache.
Tom : Enregistrement de la démonstration du module Ngx-Charts.
Corentin : Poursuite des tests et du débug.
Ergi: Finalisation de la documentation sur fullCalendar et ical4j

## 26/03 :
Corentin : Poursuite des tests et du débug 
Corentin + Tom + Maxime + Alexis + Ergi + Thibaut : Enregistrement présentation orale.

