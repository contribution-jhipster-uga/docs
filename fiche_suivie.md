#Fiche de suivie

##29/01 : 
Etablissement des rôles au sein de l’équipe
Lecture de la documentation “Création d’un module Jhipster” 
Génération d’un premier module “Test”


##31/01 :
Génération d’un projet JHipster LazyBlob.
Analyse des modules créés l’année précédente (ChatBot Rasa - Stripe).
Correction du module ChatBot Rasa.
Identification des problèmes présents sur Stripe.
Test du module ImageIA (Réseau de neurones ResNet)

##03/02 :
Rendez-vous avec Didier Donsez pour établir le cahier des charges.
Préparation des Sprints (Backlog)

##04/02 : 
Mise en commun des tâches à faire, répartition du backlog.
Ergi & Corentin : JSON-LD bloqué, envoie d’un message à Didier Donsez pour nous débloquer. Début FullCalendar et prise en main d’Angular.
Maxime : Génération des variables associées au type ImageBlob
Alexis, Thibaut, Tom : Indexation Full-Text ImageAI, OCR, Apache Tika

Développement d’une fonction de détection d’image avec ImageAI (Python + Intégration à Spring)
Développement d’une fonction de parsing metadata avec Apache Tika


##05/02 : 
Ergi & Corentin : Prise en main d’Angular et mise en place + configuration de l’API FullCalendar sur JHipster
Maxime : Zzz...Zzz...Zzz...
Alexis, Thibaut, Tom : Intégration des fonctions du module d’indexation dans une classe java Indexation. 
Traitement d’une image lors d’un ajout en BDD pour compléter les champs extractedObject, exif à l’aide des fonctions d’Indexation.



##07/02 :
 Alexis, Thibaut, Tom : Correction des fonctions d’indexation afin qu’elle fonctionne sous linux. -> Succès
 Maxime : 

 Corentin : 

Ergi : Récupération des events de la base des données pour les afficher dans fullCalendar.

##10/02 :
Rencontre avec Didier Donsez. Discussion autour du @Lazy et de la suite du projet LazyBlob.
Créer de nouveau DTOs (L’un avec tous les champs, un autre avec @Lazy)
Créer un service pour récupérer la ressource Lazy en question.

Ergi: Créer un nouveau event avec fullCalendar et l’ajouter dans la base de données.
 
##11/02 :
Ergi + Corentin: Génération d’un nouveau projet avec le modèle complète.
Alexis + Thibaut + Tom : On a étudié le code du projet Lazyblob qui gère l’appel des images avec gestion du cache.

Maxime : Absence justifiée

##12/02 : 
Alexis + Thibaut + Tom : Application et test de la route GetBlobImage à plusieurs endroits de l’application.

##13/02 :
 Alexis + Thibaut + Tom : Correction d’erreur sur le récupération des données liées à l’api.

##14/02 :
Alexis + Thibaut + Tom : Continuation des corrections d’erreur + test avec elasticsearch.

##18/02 :
Réunion avec Didier Donsez.
Alexis + Thibaut + Tom : Création d’une nouvelle entité PhotoLite pour permettre un appel Lazy au niveau du JPARepository.
Ajout du PhotoLiteRepository et du PhotoLiteMapper, modification des services et de la fonction getBlobasResponseEntity pour optimiser l’appel des images. 


##20/02 :
Alexis : Diaporama soutenance intermédiaire
Thibaut + Tom : Adaptation du front end avec PhotoLite
