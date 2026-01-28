# Projet 1 : Habilitation Active Directory

---

## I. Contexte :

Dans le cadre de ma formation et de ma montée en compétences en administration système, j’ai choisi de mettre en place une infrastructure Active Directory complète afin de comprendre et maîtriser les mécanismes d’habilitation, de gestion des utilisateurs et de sécurisation des accès. L’objectif est de simuler un environnement de l'entreprise MDF comprenant plusieurs services (Informatique, Comptabilité, Marketing) et de mettre en œuvre une gestion des permissions conforme au modèle AGDLP. 

---

## II. Présentation de l’architecture : 

L’infrastructure se compose des éléments suivants : 

- serveur glpi dédié à la gestion du parc informatique et des tickets d’assistance. Il est intégré à l’infrastructure via le domaine Active Directory, permettant l’authentification centralisée des utilisateurs (SSO) et l’inventaire automatisé des postes grâce à l’agent GLPI. Ce serveur joue un rôle essentiel dans la supervision, la maintenance et la traçabilité des équipements du parc.

- serveur Windows Server jouant le rôle de contrôleur de domaine (DC). Il héberge les services essentiels : Active Directory Domain Services (AD DS), DNS, gestion des utilisateurs, des groupes et des stratégies de sécurité. 

- domaine Active Directory structuré selon une logique professionnelle. Le domaine permet l’authentification centralisée des utilisateurs et la gestion des permissions via le modèle AGDLP. 

- unités d’organisation (OU) permettant de structurer les utilisateurs, les groupes et les postes clients. Cette organisation facilite l’application de stratégies de groupe (GPO) et la gestion des habilitations. 

- groupes globaux (GG) représentant les rôles métiers (Ressources Humaines, Informatique, Comptabilité). Ils regroupent les utilisateurs selon leur fonction. 

- groupes locaux de domaine (DLG) associés aux ressources partagées. Ils reçoivent les permissions NTFS et SMB sur les dossiers du serveur. 

- poste client Windows Pro intégrés au domaine. Il permet aux utilisateurs de se connecter avec leur compte AD et d’accéder aux ressources selon leurs droits. 

- dossiers partagés sur le serveur, organisés par service (Informatique, Comptabilité, Marketing). Chaque dossier est protégé par des permissions adaptées au rôle des utilisateurs. 

<p align="center">

<img src="architecture/01.png" width="400"> 
                                                                                                                                
</p> 

---

## III. Objectifs du projet : 

Le projet à pour objectif : 

- d'installer un serveur Windows Server,
- d'installer un domaine active directory,
- d'installer un serveur glpi,
- d'installer trois postes clients,
- de créer des unités d’organisation, 
- de créer des groupes globaux, 
- de créer des groupes locaux de domaine,
- de créer des utilisateurs,
- de créer des dossiers partages,
- de joindre les postes aux domaines.

---

## III.1. Installation Windows server et domaine active directory :

## Installation et configuration Windows server :

<p align="center">

<img src="configuration_2/01.png" width="400">

<img src="configuration_2/02.png" width="400">

<img src="configuration_2/03.png" width="400">

<img src="configuration_2/04.png" width="400">

<img src="configuration_2/05.png" width="400">

<img src="configuration_2/06.png" width="400">

<img src="configuration_2/07.png" width="400">

<img src="configuration_2/08.png" width="400">

<img src="configuration_2/09.png" width="400">

<img src="configuration_2/10.png" width="400">

<img src="configuration_2/11.png" width="400">

<img src="configuration_2/12.png" width="400">

<img src="configuration_2/13.png" width="400">

<img src="configuration_2/14.png" width="400">

<img src="configuration_2/15.png" width="400">

<img src="configuration_2/16.png" width="400">

</p>

## Installation du domaine active directory :

















---

## III.2. Installation du serveur glpi :

Prérequis à télécharger :

- WampServer (PHP version 7.4.33) 
- Packages Microsoft Visual C++ 
- GLPI version 10.0.6

## Installation WampServer :

WampServer est une plateforme de développement web pour Windows. Elle permet : de créer et tester des sites web en local, d'utiliser des technologies comme (Apache, MySQL, PHP), de gérer les bases de données avec phpMyAdmin.

<p align="center">

<img src="wampserver/01.png" width="400">

<img src="wampserver/02.png" width="400">

<img src="wampserver/03.png" width="400">

<img src="wampserver/04.png" width="400">

<img src="wampserver/05.png" width="400">

<img src="wampserver/06.png" width="400">

<img src="wampserver/07.png" width="400">

<img src="wampserver/08.png" width="400">

<img src="wampserver/09.png" width="400">

<img src="wampserver/10.png" width="400">

</p>

## Installation GLPI :

GLPI est un logiciel libre de gestion informatique (ITSM) qui permet de gérer : un parc informatique, les utilisateurs, les tickets d’assistance et l’ensemble des services IT d’une organisation. GLPI permet d’appliquer concrètement les processus ITIL dans une organisation. 

ITIL (Information Technology Infrastructure Library) est un référentiel international qui décrit les meilleures pratiques pour organiser un service informatique. Il définit des processus tels que : gestion des incidents, gestion des demandes, gestion des problèmes, gestion des changements, gestion des actifs (CMDB), gestion des connaissances, gestion du catalogue de services, suivi des SLA et qualité de service.

<p align="center">

<img src="glpi/01.png" width="400">

<img src="glpi/02.png" width="400">

<img src="glpi/03.png" width="400">

<img src="glpi/04.png" width="400">

<img src="glpi/05.png" width="400">

<img src="glpi/06.png" width="400">

<img src="glpi/07.png" width="400">

<img src="glpi/08.png" width="400">

<img src="glpi/09.png" width="400">

<img src="glpi/10.png" width="400">

<img src="glpi/11.png" width="400">

<img src="glpi/12.png" width="400">

<img src="glpi/13.png" width="400">

<img src="glpi/14.png" width="400">

</p>

---

III.3. Installation et configuration postes clients :

<p align="center">

<img src="configuration_1/01.png" width="400">

<img src="configuration_1/02.png" width="400">

<img src="configuration_1/03.png" width="400">

<img src="configuration_1/04.png" width="400">

<img src="configuration_1/05.png" width="400">

<img src="configuration_1/06.png" width="400">

<img src="configuration_1/07.png" width="400">

<img src="configuration_1/08.png" width="400">

<img src="configuration_1/09.png" width="400">

<img src="configuration_1/10.png" width="400">

<img src="configuration_1/11.png" width="400">

<img src="configuration_1/12.png" width="400">

<img src="configuration_1/13.png" width="400">

<img src="configuration_1/14.png" width="400">

<img src="configuration_1/15.png" width="400">

<img src="configuration_1/16.png" width="400">

</p>

---









