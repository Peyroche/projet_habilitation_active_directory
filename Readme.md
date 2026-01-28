# Projet 1 : Habilitation Active Directory

---

## I. Contexte :

Dans le cadre de ma formation en BTS SIO et de ma montée en compétences en administration système, j’ai choisi de mettre en place une infrastructure Active Directory complète afin de comprendre et maîtriser les mécanismes d’habilitation, de gestion des utilisateurs et de sécurisation des accès. L’objectif est de simuler un environnement de l'entreprise MDF comprenant deux services (Informatique, Comptabilité) et de mettre en œuvre une gestion des permissions conforme au modèle AGDLP. 

---

## II. Présentation de l’architecture : 

L’infrastructure se compose des éléments suivants : 

- serveur glpi dédié à la gestion du parc informatique et des tickets d’assistance. Il est intégré à l’infrastructure via le domaine Active Directory, permettant l’authentification centralisée des utilisateurs (SSO) et l’inventaire automatisé des postes grâce à l’agent GLPI. Ce serveur joue un rôle essentiel dans la supervision, la maintenance et la traçabilité des équipements du parc.

- serveur Windows Server jouant le rôle de contrôleur de domaine (DC). Il héberge les services essentiels : Active Directory Domain Services (AD DS), DNS, gestion des utilisateurs, des groupes et des stratégies de sécurité. 

- domaine Active Directory structuré selon une logique professionnelle. Le domaine permet l’authentification centralisée des utilisateurs et la gestion des permissions via le modèle AGDLP. 

- unités d’organisation (OU) permettant de structurer les utilisateurs, les groupes et les postes clients. Cette organisation facilite l’application de stratégies de groupe (GPO) et la gestion des habilitations. 

- groupes globaux (GG) représentant les rôles métiers (Ressources Humaines, Informatique, Comptabilité). Ils regroupent les utilisateurs selon leur fonction. 

- groupes locaux de domaine (DLG) associés aux ressources partagées. Ils reçoivent les permissions NTFS et SMB sur les dossiers du serveur. 

- postes clients Windows Pro intégrés au domaine. Ils permettent aux utilisateurs de se connecter avec leur compte AD et d’accéder aux ressources selon leurs droits. 

- dossiers partagés sur le serveur, organisés par service (Informatique, Comptabilité). Chaque dossier est protégé par des permissions adaptées au rôle des utilisateurs. 

---

## III. Missions réalisées : 

- installer Windows Server et le Domaine Active Directory,
- installer WampServer (Serveur GLPI),
- installer deux postes clients,
- créer des unités d’organisation, 
- créer des groupes globaux, 
- créer des groupes locaux de domaine,
- créer des utilisateurs,
- créer deux dossiers partages,
- Joindre les postes clients aux domaines.

---

## III.1. Installation Windows Server et Domaine Active Directory :

## Installation Windows Server :

<p align="center">

<img src="install_2/01.png" width="400">

<img src="install_2/02.png" width="400">

<img src="install_2/03.png" width="400">

<img src="install_2/04.png" width="400">

<img src="install_2/05.png" width="400">

<img src="install_2/06.png" width="400">

<img src="install_2/07.png" width="400">

<img src="install_2/08.png" width="400">

<img src="install_2/09.png" width="400">

<img src="install_2/10.png" width="400">

<img src="install_2/11.png" width="400">

<img src="install_2/12.png" width="400">

<img src="install_2/13.png" width="400">

<img src="install_2/14.png" width="400">

<img src="install_2/15.png" width="400">

<img src="install_2/16.png" width="400">

</p>

## Configuration Windows Server :

<p align="center">

<img src="config_1/01.png" width="400">

<img src="config_1/02.png" width="400">

<img src="config_1/03.png" width="400">

<img src="config_1/04.png" width="400">

<img src="config_1/05.png" width="400">

<img src="config_1/06.png" width="400">

</p>

## Installation Domaine Active Directory :

<p align="center">

<img src="domaine/01.png" width="400">

<img src="domaine/02.png" width="400">

<img src="domaine/03.png" width="400">

<img src="domaine/04.png" width="400">

<img src="domaine/05.png" width="400">

<img src="domaine/06.png" width="400">

<img src="domaine/07.png" width="400">

<img src="domaine/08.png" width="400">

<img src="domaine/09.png" width="400">

<img src="domaine/10.png" width="400">

<img src="domaine/11.png" width="400">

<img src="domaine/12.png" width="400">

<img src="domaine/13.png" width="400">

<img src="domaine/14.png" width="400">

<img src="domaine/15.png" width="400">

<img src="domaine/16.png" width="400">

<img src="domaine/17.png" width="400">

<img src="domaine/18.png" width="400">

<img src="domaine/19.png" width="400">

<img src="domaine/20.png" width="400">

</p>

---

## III.2. Installation du Serveur GLPI :

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

## Configuration Serveur GLPI :

<p align="center">

<img src="config_2/01.png" width="400">

<img src="config_2/02.png" width="400">

<img src="config_2/03.png" width="400">

<img src="config_2/04.png" width="400">

<img src="config_2/05.png" width="400">

<img src="config_2/06.png" width="400">

</p>

---

## III.3. Installation Postes Clients :

## III.3.1. Installation Poste Client PC01 du Service IT :

<p align="center">

<img src="install_1/01.png" width="400">

<img src="install_1/02.png" width="400">

<img src="install_1/03.png" width="400">

<img src="install_1/04.png" width="400">

<img src="install_1/05.png" width="400">

<img src="install_1/06.png" width="400">

<img src="install_1/07.png" width="400">

<img src="install_1/08.png" width="400">

<img src="install_1/09.png" width="400">

<img src="install_1/10.png" width="400">

<img src="install_1/11.png" width="400">

<img src="install_1/12.png" width="400">

<img src="install_1/13.png" width="400">

<img src="install_1/14.png" width="400">

<img src="install_1/15.png" width="400">

<img src="install_1/16.png" width="400">

</p>

## Configuration Poste Client PC01 du Service_IT :

<p align="center">

<img src="config_3/01.png" width="400">

<img src="config_3/02.png" width="400">

<img src="config_3/03.png" width="400">

<img src="config_3/04.png" width="400">

<img src="config_3/05.png" width="400">

<img src="config_3/06.png" width="400">

</p>

III.3.2. Installation Poste Client PC02 du Service_Compta :











