# PROJET 2 : HABILITATION SUR DOSSIER PARTAGE AVEC ACTIVE DIRECTORY

---

## Contexte du projet : 

Dans le cadre de ma formation et de ma montée en compétences en administration système, j’ai choisi de mettre en place une infrastructure Active Directory complète afin de comprendre et maîtriser les mécanismes d’habilitation, de gestion des utilisateurs et de sécurisation des accès. L’objectif est de simuler un environnement d’entreprise comprenant plusieurs services (Ressources Humaines, Informatique, Comptabilité) et de mettre en œuvre une gestion des permissions conforme au modèle AGDLP. 

Pour cela, j’ai installé un serveur Windows Server jouant le rôle de contrôleur de domaine, ainsi que plusieurs postes clients Windows reliés au domaine. J’ai ensuite créé des unités d’organisation, des groupes globaux, des groupes locaux de domaine et des utilisateurs, afin de structurer les droits d’accès aux dossiers partagés. Ce projet permet de reproduire une architecture professionnelle et de démontrer ma capacité à organiser, sécuriser et documenter une infrastructure Active Directory. 

--- 

## Objectifs : 

L’objectif principal de ce projet est de mettre en place une infrastructure Active Directory fonctionnelle et sécurisée permettant de gérer efficacement les utilisateurs, les groupes et les droits d’accès aux ressources partagées. Plus précisément, ce projet vise à : 

- Créer une architecture Active Directory structurée (OU, utilisateurs, groupes globaux et locaux). 

- Appliquer le modèle AGDLP afin d’assurer une gestion claire, scalable et professionnelle des habilitations. 

- Mettre en place des dossiers partagés accessibles selon les rôles (Ressources Humaines, Informatique, Comptabilité, etc.). 

- Configurer les permissions NTFS et SMB pour garantir un contrôle d’accès strict et cohérent. 

- Joindre des postes clients au domaine afin de permettre une authentification centralisée. 

- Tester et valider les accès pour chaque utilisateur selon son rôle. 

- Documenter l’ensemble du processus de manière claire, illustrée et professionnelle. 

---

## Enjeux de sécurité : 

La mise en place d’une infrastructure Active Directory implique des enjeux de sécurité importants. L’objectif est de garantir que chaque utilisateur accède uniquement aux ressources nécessaires à son rôle, tout en protégeant les données sensibles de l’entreprise. Les principaux enjeux de sécurité de ce projet sont les suivants : 

- Confidentialité des données Assurer que les informations sensibles (Ressources Humaines, Informatique, Comptabilité) ne soient accessibles qu’aux utilisateurs autorisés. Les permissions NTFS et SMB, combinées au modèle AGDLP, permettent de contrôler précisément ces accès. 

- Intégrité des informations Empêcher toute modification non autorisée des fichiers. Les droits d’écriture, de modification ou de suppression sont attribués uniquement aux groupes qui en ont besoin. 

- Traçabilité et responsabilité Chaque utilisateur possède un compte nominatif dans Active Directory. Cela permet d’identifier clairement qui accède à quoi, et de responsabiliser les actions effectuées sur les ressources partagées. 

- Réduction des risques d’erreurs humaines En centralisant la gestion des droits via AGDLP, on évite les erreurs manuelles (droits donnés directement à un utilisateur, héritages non maîtrisés, etc.). La structure devient plus lisible, plus stable et plus facile à auditer. 

- Sécurisation du réseau et des postes clients L’intégration des postes au domaine permet une authentification centralisée, l’application de stratégies de sécurité (GPO), et une meilleure protection contre les accès non autorisés. 

- Scalabilité et maintien opérationnel Une architecture bien structurée permet d’ajouter ou retirer des utilisateurs, services ou ressources sans compromettre la sécurité. Les droits sont gérés par groupes, ce qui évite les dérives et garantit une évolution propre. 

---

## Présentation de l’architecture : 

L’architecture mise en place dans le cadre de ce projet repose sur une infrastructure Active Directory centralisée, composée d’un serveur principal et de plusieurs postes clients intégrés au domaine. Cette architecture permet de simuler un environnement d’entreprise dans lequel les utilisateurs, les groupes et les ressources sont gérés de manière centralisée. 

L’infrastructure se compose des éléments suivants : 

- Un serveur Windows Server jouant le rôle de contrôleur de domaine (DC). Il héberge les services essentiels : Active Directory Domain Services (AD DS), DNS, gestion des utilisateurs, des groupes et des stratégies de sécurité. 

- Un domaine Active Directory structuré selon une logique professionnelle. Le domaine permet l’authentification centralisée des utilisateurs et la gestion des permissions via le modèle AGDLP. 

- Des unités d’organisation (OU) permettant de structurer les utilisateurs, les groupes et les postes clients. Cette organisation facilite l’application de stratégies de groupe (GPO) et la gestion des habilitations. 

- Des groupes globaux (GG) représentant les rôles métiers (Ressources Humaines, Informatique, Comptabilité). Ils regroupent les utilisateurs selon leur fonction. 

- Des groupes locaux de domaine (DLG) associés aux ressources partagées. Ils reçoivent les permissions NTFS et SMB sur les dossiers du serveur. 

- Des postes clients Windows Pro intégrés au domaine. Ils permettent aux utilisateurs de se connecter avec leur compte AD et d’accéder aux ressources selon leurs droits. 

- Des dossiers partagés sur le serveur, organisés par service (Ressources Humaines, Informatique, Comptabilité). Chaque dossier est protégé par des permissions adaptées au rôle des utilisateurs. 

---

## Répartition du Document : 

Ce document est reparti en 3 parties, à savoir :

Partie I - Création de l’architecture AD  : 

- Installation du serveur 

- Configuration du domaine 

- Ajout d’un ordinateur au domaine 

- Création dossier partagé 

- Création des OU. 

Partie II – Mise en place d’AGLDP :

- Création des comptes 

- Création des groupes GG et DLG 

- Attribution des permissions NTFS/SMB. 

Partie III – Tests et validations : 

- Connexion utilisateur 

- Accès aux dossiers 

- Vérifications des droits. 
