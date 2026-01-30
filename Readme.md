# Projet 1 : Habilitation Active Directory

---

## I. Contexte :

Dans le cadre de ma formation en BTS SIO et de ma montée en compétences en administration système, j’ai choisi de mettre en place sur un environnement virtuel VirtualBox une infrastructure Active Directory complète afin de comprendre et maîtriser les mécanismes d’habilitation, de gestion des utilisateurs et de sécurisation des accès. L’objectif est de simuler un environnement de travail du Groupe MDF comprenant deux services (Informatique, Comptabilité) et de mettre en œuvre une gestion des permissions conforme au modèle AGDLP. 

---

## II. Présentation de l’architecture : 

L’infrastructure se compose des éléments suivants : 

- serveur Windows Server jouant le rôle de contrôleur de domaine (DC). Il héberge les services essentiels : Active Directory Domain Services (AD DS), DNS, gestion des utilisateurs, des groupes et des stratégies de sécurité. 

- domaine Active Directory structuré selon une logique professionnelle. Le domaine permet l’authentification centralisée des utilisateurs et la gestion des permissions via le modèle AGDLP. 

- unités d’organisation (OU) permettant de structurer les utilisateurs, les groupes et les postes clients. Cette organisation facilite l’application de stratégies de groupe (GPO) et la gestion des habilitations. 

- groupes globaux (GG) représentant les rôles métiers (Informatique, Comptabilité). Ils regroupent les utilisateurs selon leur fonction. 

- groupes locaux de domaine (DLG) associés aux ressources partagées. Ils reçoivent les permissions NTFS et SMB sur les dossiers du serveur. 

- d'un poste client Windows Pro intégré au domaine. Il permet aux utilisateurs de se connecter avec leur compte AD et d’accéder aux ressources selon leurs droits. 

- dossiers partagés sur le serveur, organisés par service (Informatique, Comptabilité). Chaque dossier est protégé par des permissions adaptées au rôle des utilisateurs. 

---

## III. Réalisations : 

Pour en arriver au résultat de l'habilitation au travers de active directory, j’ai installé VirtualBox sur une machine physique, ensuite un serveur Windows Server jouant le rôle de contrôleur de domaine ainsi qu'un poste client Windows relié au domaine. J’ai ensuite créé des unités d’organisation, des groupes globaux, des groupes locaux de domaine et des utilisateurs, afin de structurer les droits d’accès aux dossiers partagés. Ce projet permet de reproduire une architecture professionnelle et de démontrer ma capacité à organiser, sécuriser et documenter une infrastructure Active Directory.

---

## III.1. Installations :


## Installation VirtualBox :


<p align="center">

<img src="install_VirtuelBox/01.png" width="400">

<img src="install_VirtuelBox/02.png" width="400">

<img src="install_VirtuelBox/03.png" width="400">

<img src="install_VirtuelBox/04.png" width="400">

<img src="install_VirtuelBox/05.png" width="400">

<img src="install_VirtuelBox/06.png" width="400">

<img src="install_VirtuelBox/07.png" width="400">

<img src="install_VirtuelBox/08.png" width="400">

<img src="install_VirtuelBox/09.png" width="400">

<img src="install_VirtuelBox/10.png" width="400">

<img src="install_VirtuelBox/11.png" width="400">

</p>


## Installation Windows Server et AD :


<p align="center">

<img src="install_SRV/01.png" width="400">

<img src="install_SRV/02.png" width="400">

<img src="install_SRV/03.png" width="400">

<img src="install_SRV/04.png" width="400">

<img src="install_SRV/05.png" width="400">

<img src="install_SRV/06.png" width="400">

<img src="install_SRV/07.png" width="400">

<img src="install_SRV/08.png" width="400">

<img src="install_SRV/09.png" width="400">

<img src="install_SRV/10.png" width="400">

<img src="install_SRV/11.png" width="400">

<img src="install_SRV/12.png" width="400">

<img src="install_SRV/13.png" width="400">

<img src="install_SRV/14.png" width="400">

<img src="install_SRV/15.png" width="400">

<img src="install_SRV/16.png" width="400">

<img src="install_SRV/17.png" width="400">

<img src="install_SRV/18.png" width="400">

<img src="install_SRV/19.png" width="400">

<img src="install_SRV/20.png" width="400">

</p>


## Installation du poste client :


<p align="center">

<img src="install_PC/01.png" width="400">

<img src="install_PC/02.png" width="400">

<img src="install_PC/03.png" width="400">

<img src="install_PC/04.png" width="400">

<img src="install_PC/05.png" width="400">

<img src="install_PC/06.png" width="400">

<img src="install_PC/07.png" width="400">

<img src="install_PC/08.png" width="400">

<img src="install_PC/09.png" width="400">

<img src="install_PC/10.png" width="400">

</p>


## III.2. Configurations :


## Configuration VirtualBox :


<p align="center">

<img src="config_VirtuelBox/01.png" width="400">

<img src="config_VirtuelBox/02.png" width="400">

</p>


## Configuration Windows server :





## Configuration et jonction du poste client au domaine :




## III.3. Application méthode AGDLP :


