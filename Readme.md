# Projet 1 : Habilitation_AD

---

## Présentation de l’architecture : 

L’architecture mise en place dans le cadre de ce projet repose sur une infrastructure Active Directory centralisée, composée d’un serveur principal et d'un poste client intégré au domaine. Cette architecture permet de simuler un environnement d’entreprise dans lequel les utilisateurs, les groupes et les ressources sont gérés de manière centralisée. 

L’infrastructure se compose des éléments suivants : 

- 1 serveur Windows Server jouant le rôle de contrôleur de domaine (DC). Il héberge les services essentiels : Active Directory Domain Services (AD DS), DNS, gestion des utilisateurs, des groupes et des stratégies de sécurité. 

- 1 domaine Active Directory structuré selon une logique professionnelle. Le domaine permet l’authentification centralisée des utilisateurs et la gestion des permissions via le modèle AGDLP. 

- 3 unités d’organisation (OU) permettant de structurer les utilisateurs, les groupes et les postes clients. Cette organisation facilite l’application de stratégies de groupe (GPO) et la gestion des habilitations. 

- 3 groupes globaux (GG) représentant les rôles métiers (Ressources Humaines, Informatique, Comptabilité). Ils regroupent les utilisateurs selon leur fonction. 

- 3 groupes locaux de domaine (DLG) associés aux ressources partagées. Ils reçoivent les permissions NTFS et SMB sur les dossiers du serveur. 

- 1 poste client Windows Pro intégrés au domaine. Il permet aux utilisateurs de se connecter avec leur compte AD et d’accéder aux ressources selon leurs droits. 

- 3 dossiers partagés sur le serveur, organisés par service (Ressources Humaines, Informatique, Comptabilité). Chaque dossier est protégé par des permissions adaptées au rôle des 
utilisateurs. 

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

## Répartition du Document : 

Ce projet est reparti en 2 parties, à savoir :


Partie I – Mise en place d’AGLDP :

- Création des comptes utilisateurs

- Création des GG et DLG 

- Attributions des permissions NTFS

- Attributions des droits de partage SMB.


Partie II - Réseaux

- Activation carte réseau

- Configuration réseau

- Jonction du poste client

- Tests de configuration
 

Partie III – Tests et validations : 

- Connexion des utilisateurs au domaine

- Vérifications accès et permissions NTFS.
