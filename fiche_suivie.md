#Fiche de suivie

##29/01 : 
Etablissement des r�les au sein de l��quipe
Lecture de la documentation �Cr�ation d�un module Jhipster� 
G�n�ration d�un premier module �Test�


##31/01 :
G�n�ration d�un projet JHipster LazyBlob.
Analyse des modules cr��s l�ann�e pr�c�dente (ChatBot Rasa - Stripe).
Correction du module ChatBot Rasa.
Identification des probl�mes pr�sents sur Stripe.
Test du module ImageIA (R�seau de neurones ResNet)

##03/02 :
Rendez-vous avec Didier Donsez pour �tablir le cahier des charges.
Pr�paration des Sprints (Backlog)

##04/02 : 
Mise en commun des t�ches � faire, r�partition du backlog.
Ergi & Corentin : JSON-LD bloqu�, envoie d�un message � Didier Donsez pour nous d�bloquer. D�but FullCalendar et prise en main d�Angular.
Maxime : G�n�ration des variables associ�es au type ImageBlob
Alexis, Thibaut, Tom : Indexation Full-Text ImageAI, OCR, Apache Tika

D�veloppement d�une fonction de d�tection d�image avec ImageAI (Python + Int�gration � Spring)
D�veloppement d�une fonction de parsing metadata avec Apache Tika


##05/02 : 
Ergi & Corentin : Prise en main d�Angular et mise en place + configuration de l�API FullCalendar sur JHipster
Maxime : Zzz...Zzz...Zzz...
Alexis, Thibaut, Tom : Int�gration des fonctions du module d�indexation dans une classe java Indexation. 
Traitement d�une image lors d�un ajout en BDD pour compl�ter les champs extractedObject, exif � l�aide des fonctions d�Indexation.



##07/02 :
 Alexis, Thibaut, Tom : Correction des fonctions d�indexation afin qu�elle fonctionne sous linux. -> Succ�s
 Maxime : 

 Corentin : 

Ergi : R�cup�ration des events de la base des donn�es pour les afficher dans fullCalendar.

##10/02 :
Rencontre avec Didier Donsez. Discussion autour du @Lazy et de la suite du projet LazyBlob.
Cr�er de nouveau DTOs (L�un avec tous les champs, un autre avec @Lazy)
Cr�er un service pour r�cup�rer la ressource Lazy en question.

Ergi: Cr�er un nouveau event avec fullCalendar et l�ajouter dans la base de donn�es.
 
##11/02 :
Ergi + Corentin: G�n�ration d�un nouveau projet avec le mod�le compl�te.
Alexis + Thibaut + Tom : On a �tudi� le code du projet Lazyblob qui g�re l�appel des images avec gestion du cache.

Maxime : Absence justifi�e

##12/02 : 
Alexis + Thibaut + Tom : Application et test de la route GetBlobImage � plusieurs endroits de l�application.

##13/02 :
 Alexis + Thibaut + Tom : Correction d�erreur sur le r�cup�ration des donn�es li�es � l�api.

##14/02 :
Alexis + Thibaut + Tom : Continuation des corrections d�erreur + test avec elasticsearch.

##18/02 :
R�union avec Didier Donsez.
Alexis + Thibaut + Tom : Cr�ation d�une nouvelle entit� PhotoLite pour permettre un appel Lazy au niveau du JPARepository.
Ajout du PhotoLiteRepository et du PhotoLiteMapper, modification des services et de la fonction getBlobasResponseEntity pour optimiser l�appel des images. 


##20/02 :
Alexis : Diaporama soutenance interm�diaire
Thibaut + Tom : Adaptation du front end avec PhotoLite
