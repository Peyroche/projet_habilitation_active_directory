# PROJET 2 : HABILITATION SUR DOSSIER PARTAGE AVEC AD

---

## Contexte du projet : 

Dans le cadre de ma formation et de ma montée en compétences en administration système, j’ai choisi de mettre en place une infrastructure Active Directory complète afin de comprendre et maîtriser le mécanisme d’habilitation, de gestion utilisateur et de sécurisation des accès. L’objectif est de simuler un environnement d’entreprise comprenant un service Ressources Humaines et de mettre en œuvre une gestion des permissions conforme au modèle AGDLP. 

Pour cela, j’ai installé un serveur Windows Server jouant le rôle de contrôleur de domaine, ainsi qu'un poste client Windows relié au domaine. J’ai ensuite créé des unités d’organisation, un groupe global, un groupe local de domaine et un utilisateur, afin de structurer les droits d’accès au dossier partagé. Ce projet permet de reproduire une architecture professionnelle et de démontrer ma capacité à organiser, sécuriser et documenter une infrastructure Active Directory. 

--- 

## Objectifs : 

L’objectif principal de ce projet est de mettre en place une infrastructure Active Directory fonctionnelle et sécurisée permettant de gérer efficacement un utilisateur, son groupe et ses droits d’accès aux ressources partagées. Plus précisément, ce projet vise à : 

- Créer une architecture Active Directory structurée (OU, utilisateur, groupe global et local). 

- Appliquer le modèle AGDLP afin d’assurer une gestion claire, scalable et professionnelle des habilitations. 

- Mettre en place un dossier partagé accessible selon le rôle Ressources Humaines. 

- Configurer les permissions NTFS et SMB pour garantir un contrôle d’accès strict et cohérent. 

- Joindre un poste client au domaine afin de permettre une authentification centralisée. 

- Tester et valider l'accès pour un utilisateur selon son rôle. 

- Documenter l’ensemble du processus de manière claire, illustrée et professionnelle. 

---

## Enjeux de sécurité : 

La mise en place d’une infrastructure Active Directory implique des enjeux de sécurité importants. L’objectif est de garantir que l'utilisateur accède uniquement aux ressources nécessaires à son rôle, tout en protégeant les données sensibles de l’entreprise. Les principaux enjeux de sécurité de ce projet sont les suivants : 

- Confidentialité des données : Assurer que les informations sensibles Ressources Humaines ne soit accessibles qu'à l'utilisateur autorisé. Les permissions NTFS et SMB, combinées au modèle AGDLP, permettent de contrôler précisément ces accès. 

- Intégrité des informations : Empêcher toute modification non autorisée des fichiers. Les droits d’écriture, de modification ou de suppression sont attribués uniquement aux groupes qui en ont besoin. 

- Traçabilité et responsabilité : L'utilisateur possède un compte nominatif dans Active Directory. Cela permet d’identifier clairement qui accède à quoi, et de responsabiliser les actions effectuées sur les ressources partagées. 

- Réduction des risques d’erreurs humaines En centralisant la gestion des droits via AGDLP, on évite les erreurs manuelles (droits donnés directement à un utilisateur, héritages non maîtrisés, etc.). La structure devient plus lisible, plus stable et plus facile à auditer. 

- Sécurisation du réseau et du poste client : L’intégration du poste au domaine permet une authentification centralisée, l’application de stratégies de sécurité (GPO), et une meilleure protection contre les accès non autorisés. 

- Scalabilité et maintien opérationnel Une architecture bien structurée permet d’ajouter ou retirer des utilisateurs, services ou ressources sans compromettre la sécurité. Les droits sont gérés par groupes, ce qui évite les dérives et garantit une évolution propre. 

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

- Connexion utilisateur au domaine

- Accès au dossier partage

- Vérifications des permissions NTFS.
