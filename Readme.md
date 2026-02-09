## PROJET 2 : MISE EN PLACE ET VERIFICATION DES NIVEAUX D'HABILITATION SUR UN DOSSIER PARTAGE WINDOWS (ACTIVE DIRECTORY)
---

## I. Introduction 

Dans un environnement professionnel, la gestion des droits d’accès aux ressources est un élément essentiel de la sécurité informatique. Les entreprises doivent garantir que chaque collaborateur accède uniquement aux informations nécessaires à l’exercice de ses fonctions.
Ce projet consiste à mettre en place un dossier partagé au sein d’un domaine Active Directory, à définir des niveaux d’habilitation adaptés aux différents services, puis à vérifier automatiquement la conformité de ces droits grâce à un script PowerShell.

Ce travail s’inscrit dans une démarche de sécurisation du système d’information et répond aux bonnes pratiques de gestion des accès en entreprise.

---

## II. Problématique  

Comment garantir que les utilisateurs d’un domaine Active Directory disposent uniquement des droits nécessaires à leur activité, tout en assurant une gestion centralisée, cohérente et vérifiable des habilitations sur un dossier partagé ?

Cette problématique implique :

- la création d’une structure AD propre et hiérarchisée,

- la mise en place de groupes de sécurité adaptés,

- l’application de droits NTFS cohérents,

- la vérification régulière de la conformité des habilitations.

---

## III. Objectifs du projet 

Objectif principal :

- Mettre en place un dossier partagé sécurisé et vérifier automatiquement les habilitations associées aux différents services.

Objectifs détaillés :

- Créer un domaine Active Directory fonctionnel.

- Organiser les utilisateurs dans des unités d’organisation (OU).

- Créer des groupes de sécurité correspondant aux services.

- Configurer un dossier partagé avec des droits NTFS adaptés.

- Automatiser la vérification des droits via un script PowerShell.

- Générer un rapport indiquant la conformité ou les écarts détectés

---

IV. Enjeux du projet

Sécurité :

- Limiter l’accès aux données sensibles et réduire les risques de fuite ou de manipulation non autorisée.

Organisation :

- Structurer les services et les groupes pour faciliter la gestion quotidienne des comptes utilisateurs.

Automatisation :

- Éviter les erreurs humaines grâce à un script de vérification automatique.

Traçabilité :

- Produire un rapport d’audit permettant de prouver la conformité des habilitations.

Conformité :

- Respecter les bonnes pratiques de sécurité (principe du moindre privilège).

---

V. Déroulement du projet

Afin de répondre efficacement à la problématique de gestion des habilitations au sein d’un domaine Active Directory, il a été nécessaire de structurer une démarche méthodique et progressive. La mise en place d’un environnement de test, la création d’une organisation cohérente dans l’annuaire, puis l’application de droits d’accès adaptés constituent les fondations essentielles de ce projet.

1. Mise en place de l’environnement
- Installation d’un contrôleur de domaine Windows Server sous VirtualBox,
- Création du domaine : mdf.local,
- Ajout d’un poste client Windows 10 au domaine.

2. Organisation de l’Active Directory
- Création des OU,
- Création des groupes de sécurité,
- Création des utilisateurs et affectation aux groupes

3. Mise en place du dossier partagé
- Création du dossier D:\Services.
- Sous-dossiers : RH, Comptabilité, Informatique,
- Partage du dossier principal,
- Application des droits NTFS.

4. Vérification automatique des habilitations

Création d’un script PowerShell permettant de :
- lire les ACL des dossiers,
- comparer les droits réels aux droits attendus,
- afficher un résultat conforme / non conforme.

5. Tests et validation
- Connexion avec un utilisateur RH → accès uniquement au dossier RH.
- Connexion avec un utilisateur Comptabilité → accès uniquement à Comptabilité.
- Connexion avec un utilisateur IT → accès lecture globale.
- Exécution du script PowerShell → génération d’un rapport d’audit.

---

## III. Réalisations : 

### 1. Mise en place de l'environnement

### Installation d’un contrôleur de domaine Windows Server sous VirtualBox

<p align="center">

<img src="install_serveur/01.png" width="400">

<img src="install_serveur/02.png" width="400">

<img src="install_serveur/03.png" width="400">

<img src="install_serveur/04.png" width="400">

<img src="install_serveur/05.png" width="400">

<img src="install_serveur/06.png" width="400">

<img src="install_serveur/07.png" width="400">

<img src="install_serveur/08.png" width="400">

<img src="install_serveur/09.png" width="400">

<img src="install_serveur/10.png" width="400">

</p>

### Création du domaine 

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

### Ajout d’un poste client Windows 10 au domaine

