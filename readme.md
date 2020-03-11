# Prosit – aller – 4 - modélisation de systèmes

## Mots clés :

- Procédure de développement

- Mise en production

- Test fonctionnelle

- Rapport de test fonctionnel

- Production

- Build

- Nombre d’anomalies

- Fonctionnalités

- Erreurs
- urbanisation = modifier le mode de fonctionnement des services de l'entreprise

- Processus métier : ensemble d'activité correlées qui contribuent aux finalités des affaires d'une organisation

- **_BPMN 2.0 (à définir)_** : Business Process Model and Notation  est une méthode de modélisation graphique de processus métier. Elle est décrite dans la norme ISO 19510.

- **_Maven_** : outils de gestion d'automatisation des projets logiciels Java. beaucoup utilisé pour auto l'intégration continue. Les étapes du cycle de vie : compile,  test, package, install, deploy

- **_Jenkins_**: outil open source d'intégration continue. Il s'interface avec des outils de versionning et permet d'exécuter des projets basés sur Ant ou Maven et des script shell ou batch

- BPEL : Conçu par IBM, BEA et Microsoft et basé sur le BPML, c’est la représentation XML d’un processus exécutable, qui peut être déployée sur n’importe quel moteur de processus métier. L’élément premier d’un processus BPEL est une « activité », qui peut être l’envoi d’un message, la réception d’un message, l’appel d’une opération (envoi d’un message, attente d’une réponse), ou une transformation de données.

## Contexte :

### Qui

Entreprise éditrice de solution logicielle

### Quoi

Améliorer ses procédure développement et mise en production

### Comment

Modéliser ses process pour les simplifier

Inclure le plus de modifications pour les tests

### Pourquoi

Diminuer le nombre d’anomalies

Réduire le temps de développement

## Contraintes :

Maven ?

JUnit ?

Java ?

## Problématiques :

Comment améliorer le processus de développement et de mise en production ?

Comment permettre à l’équipe de développement de continuer le travail en attendant le rapport d’erreur ?

Comment diminuer le nombre d’anomalie en lisant un diagramme ?

## Généralisation :

Optimisation

Organisation

Modélisation

Diminuer le nombre d’anomalie

## Hypothèses :

Le dev de test unitaire peut accélérer l’exécution des tests fonctionnel

Le BPMN est un outil qui permet de modéliser la chaine de production

BPMN est un outil qui permet d’identifier les points bloquant lors du développement et de la mise en production.

BPMN est un outil dans lequel il existe des design pattern

## Plan d’action :

### Business Process Diagram


diagramme de collaboration/communication : permet de modéliser les processus et les interactions entre 2 entités minimum.
c'est un version simplifiée du diagramme de séquence qui se concentre sur l'échange de message entre les objets et où la chronologie n'est qu'annexe
![Fig 2_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%202_CA_BPMS.jpg)


**composants d'un diagramme**
- activités : permet d'id un processus, un sous-processus ou une tâche. Un icone permet de comprendre à quel niveau nous sommes (+ pour les sous-process et des icones complémentaires peuvent distinguer les différents types de tâches (manuel, auto, soumis à une règle métier, envoi, réception, ...)
- ![Fig 3_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%203_CA_BPMS.jpg)

- bassin et couloirs : un diag de collaboration ne contient qu'un seul bassin (représentent les participants/reponsabilités: département, service), il peut contenir plusieurs couloirs qui correspondent à des rôles : manager, assistant, collaborateur. Pour chaque couloir des activités sont définies. Pour illustrer des échanges entre 2 couloirs on utilise des flux de message

![Fig 4_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%204_CA_BPMS.jpg)

- événement : un event déclenche une action ou le résultat d'un action. BPMN met à dispo 3 catégories d'event : event de début, de fin et intermédiaires. représentéspardescercles avec symboles
![Fig 5_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%205_CA_BPMS.jpg)

- connecteurs : ils permettent d'interpéter les flux : ET, OU, XOR, dans un losange

![Fig 6_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%206_CA_BPMS.jpg)

- Artefact  : 
objets aditionnels utilisées utilisés pour mieux comprendre le schéma come les activités de même catégories, les données traitées ou des commentaires

![Fig 7_CA_BPMS.jpg](http://www.bpms.info/wp-content/uploads/methodes/BPMN/Fig%207_CA_BPMS.jpg)

conversation : ensemble de message échangés


il y a aussi
-  le diagramme d'orchestration : 
- le diag de conversion : version informelle du diagramme de collaboration
- diag de chorégraphie : modélise un comportement attendu entre les participants qui interagissent les uns avec les autres

- Quoi


- Comment

- Pourquoi

### BPMN 2.0

Business Process Model and Notation  est une méthode de modélisation graphique de processus métier.
Elle est décrite dans la norme ISO 19510.

elle a été dev par la BPMI (Business Prosses Managemen Initiative) et est maintenue par l'OMG (Object Management Group) depuis leur fusion en 2005. La dernière version 2.0.2 date de 2013

### Quoi

son but est de fournir une notation simple et compréhensible par tous les utilisateurs de l'enteprise, de l'analyste métier à ceux qui vont mettre les processus métiers en place en passant par le de responsable de mettre en place la technologie des processus application.

UML et BPMN sont toutes les 2 élaborées par l'OMG et sont complémentaires. UML insiste sur l'analyse et la conception d'un système d'information et BPMN vise l'analyse et la conception de processus métiers qui font intervenir et interagir des systèmes

BPMN repose sur trois types de modèles

-   Modèle de processus : pour représenter le déroulement des processus internes d'une organisation ainsi que les processus publics (c'est-à-dire s'interfaçant avec des activités de tiers externes).
-   Modèle de collaboration : pour représenter les processus de plusieurs entités et les échanges permettant de relier ces processus
-   Modèle de chorégraphie : pour représenter les comportements attendus des acteurs dans un processus

BPMN permet de représenter les les procédures d'entrerprise internes et les procédres B2B  via les processus publics et des chorégraphies

BPMN 2.0 veut devenir un language de modélisation exécutable en remplacement de BPEL, avant il fallait mapper à la main BPMN 1.X  avec BPEL pour exécuter les processus modélisés.

### Historique

-   La première version de BPMN est livrée par la BPMI en mai 2004 initialement sous la désignation  _Business Process Modeling Notation_
-   En février 2006, l'OMG adopte la version 1.0
-   En janvier 2008, l'OMG livre la version 1.1
-   En janvier 2009, l'OMG livre la version 1.2
-   En janvier 2011, l'OMG livre la version 2.0. Celle-ci introduit des changements majeurs, notamment avec l'introduction de diagrammes de conversation et de diagrammes de chorégraphie, et une plus grande richesse dans la spécification des événements. Elle introduit également des formats d'échange de modèles
-   En juillet 2013, l'ISO adopte la version 2.02 comme norme internationale ISO/CEI 19510:2013 sous le titre "_Technologies de l'information - Modèle de procédé d'affaire et notation de l'OMG_" (en anglais "_Information technology - Object Management Group Business Process Model and Notation_")
-   En décembre 2013, l'OMG entérine la version 2.0.2, qui ne contient que des changements mineurs concernant les fichiers d'échange de modèles en XML

### Design Pattern dans BPD et BPMN

les Process partern de BPM fournissent des techniques simple et fiables qui racourcissent la courbe d'apprentissage et augmentent la productivité et la qualité. Ils pevent être combinés pour former un process complet.

Les patterns sont groupés en 6 catégories :
- Procedural patterns
- Advanced Branching and Synchronisation pattern
- structural patters
- multiple instance patterns
- state based patterns
- cancellation pattern

Procéduraux :
- la classe la plus commune. 

- patten de séquence, simple merge pattern

pattern de branchement et de synchronisation : 

- choix multiples et synchro

- collaboration pattern

multiple instane

- state based : 
Deferred Choice Pattern

- cancellation patterns :
cancel activity pattern

les trucs cons : 

xor, simple merge


autre source : 

- basic control pattern
	- sequence pattern
	- exclusive choice pattern
	- simple merge
- parallel split and synchronization pattern :
	-  



## A faire :

### Optimiser le schéma du prosit
