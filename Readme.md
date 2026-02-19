## PROJET 2 : HABILITATION SUR UN DOSSIER PARTAGE

---

## I. Introduction 

<p>Dans un environnement professionnel, la gestion des droits d’accès aux ressources est un élément essentiel de la sécurité informatique. Les entreprises doivent garantir que chaque collaborateur accède uniquement aux informations nécessaires à l’exercice de ses fonctions.</p>
<p>Ce projet consiste à mettre en place un dossier partagé au sein d’un domaine Active Directory, à définir des niveaux d’habilitation adaptés aux différents services, puis à vérifier automatiquement la conformité de ces droits grâce à un script PowerShell.</p>

<p>Ce travail s’inscrit dans une démarche de sécurisation du système d’information et répond aux bonnes pratiques de gestion des accès en entreprise.</p>

---

## II. Problématique  

Comment garantir que les utilisateurs d’un domaine Active Directory disposent uniquement des droits nécessaires à leur activité, tout en assurant une gestion centralisée, cohérente et vérifiable des habilitations sur un dossier partagé ?

Cette problématique implique :

- la création d’une structure AD propre et hiérarchisée,

- la mise en place de groupes de sécurité adaptés,

- l’application de droits NTFS cohérents,

- la vérification régulière de la conformité des habilitations.

---

## III. Objectifs

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

## IV. Enjeux

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

## V. Contexte d'intervention

<p>Dans le cadre de gestion des habilitations une procédure d'intervention a été réalisée :</p>

<p><b>1. Mise en place de l’environnement :</b></p>
<p>Installation d’un contrôleur de domaine Windows Server sous VirtualBox</p>
<p>Création du domaine mdf.local</p>
<p>Ajout d’un poste client Windows 10 au domaine.</p>

<p><b>2. Organisation de l’Active Directory :</b></p>
<p>Création des OU</p>
<p>Création des groupes de sécurité</p>
<p>Création des utilisateurs</p>
<p>Affectation des utilisateurs aux groupes globaux</p>
<p>Affectation des groupes globaux aux groupes domaines locaux.</p>

<p><b>3. Mise en place du dossier partagé</b></p>
<p>Création du dossier RH</p>
<p>Application droits de partages SMB</p>
<p>Application des permissions NTFS.</p>

<p><b>4. Exécution d'un script PowerShell de vérification automatique des habilitations.</b></p>

<p><b>5. Tester la connexion avec un utilisateur RH.</b></p>

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

### Création d'un domaine mdf.local

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

<p align="center">

<img src="ajout_PC02/01.png" width="400">

<img src="ajout_PC02/02.png" width="400">

<img src="ajout_PC02/03.png" width="400">

<img src="ajout_PC02/04.png" width="400">

<img src="ajout_PC02/05.png" width="400">

<img src="ajout_PC02/06.png" width="400">

<img src="ajout_PC02/07.png" width="400">

<img src="ajout_PC02/08.png" width="400">

<img src="ajout_PC02/09.png" width="400">

<img src="ajout_PC02/10.png" width="400">

<img src="ajout_PC02/11.png" width="400">

<img src="ajout_PC02/12.png" width="400">

</p>

### 2. Organisation de l’Active Directory
  
| Secteur              | OU_Utilisateurs      | OU_GG               | OU_DLG           |                          
|----------------------|----------------------|---------------------|------------------|
| RH                   | Placide              | GG_RH               | DLG_RH           | 
| Comptabilité         | Virginie             | GG_Compta           | DLG_Compta       | 
| Informatique         | Mercier              | GG_IT               | DLG_IT           | 

### Création des unités d'organisation (OU)

<p align="center">

<img src="OU/01.png" width="400">

<img src="OU/02.png" width="400">

<img src="OU/03.png" width="400">

<img src="OU/04.png" width="400">

</p>

### Création des groupes de sécurité

<p align="center">

<img src="GG_DLG/01.png" width="400">

<img src="GG_DLG/02.png" width="400">

<img src="GG_DLG/03.png" width="400">

<img src="GG_DLG/04.png" width="400">

<img src="GG_DLG/05.png" width="400">

<img src="GG_DLG/06.png" width="400">

</p>

### Création des utilisateurs

<p align="center">

<img src="utilisateurs/01.png" width="400">

<img src="utilisateurs/02.png" width="400">

<img src="utilisateurs/03.png" width="400">

<img src="utilisateurs/04.png" width="400">

<img src="utilisateurs/05.png" width="400">

</p>

### Affectation des utilisateurs aux groupes globaux

<p align="center">

<img src="affectation_utilisateurs/01.png" width="400">

<img src="affectation_utilisateurs/02.png" width="400">

<img src="affectation_utilisateurs/03.png" width="400">

</p>

### Affectation des groupes globaux aux groupes domaines locaux

<p align="center">

<img src="affectation_GG/01.png" width="400">

<img src="affectation_GG/02.png" width="400">

<img src="affectation_GG/03.png" width="400">

</p>

### 3. Mise en place du dossier partagé

### Création du dossier RH

<p align="center">

<img src="dossier_RH/01.png" width="400">

<img src="dossier_RH/02.png" width="400">

<img src="dossier_RH/03.png" width="400">

<img src="dossier_RH/04.png" width="400">

<img src="dossier_RH/05.png" width="400">

<img src="dossier_RH/06.png" width="400">

<img src="dossier_RH/07.png" width="400">

<img src="dossier_RH/08.png" width="400">

<img src="dossier_RH/09.png" width="400">

<img src="dossier_RH/1O.png" width="400">

<img src="dossier_RH/11.png" width="400">

</p>

### Droits de partages SMB

<p align="center">

<img src="SMB/01.png" width="400">

<img src="SMB/02.png" width="400">

<img src="SMB/03.png" width="400">

<img src="SMB/04.png" width="400">

<img src="SMB/05.png" width="400">

<img src="SMB/06.png" width="400">

<img src="SMB/07.png" width="400">

<img src="SMB/08.png" width="400">

</p>

### Permissions NTFS

<p align="center">

<img src="NTFS/01.png" width="400">

<img src="NTFS/02.png" width="400">

<img src="NTFS/03.png" width="400">

<img src="NTFS/04.png" width="400">

<img src="NTFS/05.png" width="400">

<img src="NTFS/06.png" width="400">

<img src="NTFS/07.png" width="400">

<img src="NTFS/08.png" width="400">

<img src="NTFS/09.png" width="400">

<img src="NTFS/1O.png" width="400">

<img src="NTFS/11.png" width="400">

</p>

### 4. Exécution d'un script PowerShell de vérification automatique des habilitations

<p align="center">

<img src="script/01.png" width="400">

</p>

### 5. Tester la connexion avec un utilisateur RH

<p align="center">

<img src="connexion/01.png" width="400">

<img src="connexion/02.png" width="400">

<img src="connexion/03.png" width="400">

<img src="connexion/04.png" width="400">

<img src="connexion/05.png" width="400">

<img src="connexion/06.png" width="400">

<img src="connexion/07.png" width="400">

<img src="connexion/08.png" width="400">

</p>
