## Projet 2 : Habilitation sur un dossier partage

---

## I. Présentation du projet 

<p>Dans un environnement professionnel, la gestion des droits d’accès aux ressources est un élément essentiel de la sécurité informatique. Les entreprises doivent garantir que chaque collaborateur accède uniquement aux informations nécessaires à l’exercice de ses fonctions.</p>
<p>Ce projet consiste à mettre en place un dossier partagé au sein d’un domaine Active Directory, à définir des niveaux d’habilitation adaptés aux différents services, puis à vérifier automatiquement la conformité de ces droits grâce à PowerShell.</p>

<p>Ce travail s’inscrit dans une démarche de sécurisation du système d’information et répond aux bonnes pratiques de gestion des accès en entreprise.</p>

---

## II. Problématique  

<p>Dans un environnement professionnel, la gestion des droits d’accès constitue un enjeu majeur de sécurité. Une mauvaise configuration des habilitations peut entraîner des risques importants : accès non autorisé à des données sensibles, fuites d’informations, non‑conformité réglementaire ou encore perturbation du fonctionnement des services.</p>
<p>Or, dans de nombreuses organisations, les droits sur les dossiers partagés évoluent régulièrement (arrivées, départs, changements de poste), ce qui rend difficile leur contrôle manuel.</p>

<p>La problématique est donc la suivante : Comment mettre en place une gestion fiable, sécurisée et automatisée des droits d’accès à un dossier partagé dans un domaine Active Directory, tout en garantissant la conformité des habilitations grâce à un contrôle automatisé ?</p>

---

## III. Objectifs

<p><b>1. Créer un dossier partagé sécurisé dans un domaine Active Directory</b></p>
<p>Définir une arborescence claire et adaptée aux besoins métiers</p>
<p>Configurer les partages réseau et les permissions NTFS.</p>

<p><b>2. Mettre en place des groupes d’habilitation cohérents</b></p>
<p>Créer des groupes AD correspondant aux services ou rôles</p>
<p>Appliquer le principe du moindre privilège (Least Privilège Access).</p>

<p><b>3. Automatiser la vérification des droits d’accès</b></p>

<p>Développer un script PowerShell capable :</p>
<p>Analyser les permissions du dossier</p>
<p>Comparer les droits réels avec les droits attendus</p>
<p>Signaler les écarts ou anomalies.</p>

<p><b>4. Renforcer la sécurité du système d’information</b></p>
<p>Réduire les risques d’accès non autorisés</p>
<p>Garantir la conformité des habilitations dans le temps</p>
<p>Faciliter les audits internes ou externes.</p>

<p><b>5. Simplifier la gestion quotidienne des administrateurs</b></p>
<p>Centraliser la gestion via Active Directory</p>
<p>Automatiser les contrôles pour gagner du temps et éviter les erreurs humaines.</p>

---

## IV. Architecture

| Secteur              | OU_Utilisateurs      | OU_GG               | OU_DLG           | Dossier partagé | Domain computers  |                     
|----------------------|----------------------|---------------------|------------------|-----------------|-------------------|
| RH                   | Placide              | GG_RH               | DLG_RH           | Dossier_RH      |     PC01-RH       |
| Comptabilité         | Virginie             | GG_Compta           | DLG_Compta       |     /           |        /          |
| Informatique         | Mercier              | GG_IT               | DLG_IT           |     /           |        /          |

---

## V. Procédure

<p>Dans le cadre de la gestion des habilitations dossier partage, une procédure d'intervention a été réalisée :</p>

<p><b>1. Mise en place de l’environnement</b></p>
<p>- Installation d’un contrôleur de domaine Windows</p>
<p>- Création du domaine mdf.local</p>
<p>- Ajout d’un poste client windows 10 au domaine.</p>

<p><b>2. Organisation de l’Active Directory</b></p>
<p>- Création des OU</p>
<p>- Création des groupes de sécurité</p>
<p>- Création des utilisateurs</p>
<p>- Affectation des utilisateurs aux groupes globaux</p>
<p>- Affectation des groupes globaux aux groupes domaines locaux.</p>

<p><b>3. Mise en place du dossier partagé</b></p>
<p>- Création d'un disque dur</p>
<p>- Création du dossier RH</p>
<p>- Application droits de partages SMB</p>
<p>- Application des permissions NTFS.</p>

<p><b>4. Vérification automatique des habilitations avec PowerShell.</b></p>
<p>- Vérifications des droits de partages</p>
<p>- Vérifications des permissions NTFS</p>
<p>- Vérification de l'héritage.</p>

<p><b>5. Tester l'accès réellement</b></p>
<p>- Se connecter avec un utilisateur du domaine</p> 

---

## VI. Réalisations 

### 1. Mise en place de l'environnement

### Installation Windows Server

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

</p>

### Ajout d’un poste client windows 10 Entreprise au domaine

<p align="center">

<img src="ajout_PC02/01.png" width="400">

<img src="ajout_PC02/02.png" width="400">

<img src="ajout_PC02/03.png" width="400">

<img src="ajout_PC02/04.png" width="400">

<img src="ajout_PC02/05.png" width="400">

<img src="ajout_PC02/06.png" width="400">

<img src="ajout_PC02/07.png" width="400">

<img src="ajout_PC02/08.png" width="400">

</p>

### 2. Organisation de l’Active Directory
  
### Création des unités d'organisation (OU)

<p align="center">

<img src="OU/01.png" width="400">

<img src="OU/02.png" width="400">

<img src="OU/03.png" width="400">

<img src="OU/04.png" width="400">

</p>

### Création des groupes globaux et domaines locaux

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

### Création disque dur

<p align="center">

<img src="disque_dur/01.png" width="400">

<img src="disque_dur/02.png" width="400">

<img src="disque_dur/03.png" width="400">

<img src="disque_dur/04.png" width="400">

<img src="disque_dur/05.png" width="400">

<img src="disque_dur/06.png" width="400">

<img src="disque_dur/07.png" width="400">

<img src="disque_dur/08.png" width="400">

<img src="disque_dur/09.png" width="400">

<img src="disque_dur/10.png" width="400">

<img src="disque_dur/11.png" width="400">

<img src="disque_dur/12.png" width="400">

</p>

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

</p>

### Droits de partages SMB

Les droits de partages sont présentés sur ce tableau :

<div align="center">

| Groupes                | Rôles                 | Droits               |                      
|------------------------|-----------------------|----------------------|
| domaine computers      | PC du domaine         | lecture              |
| DLG_RH                 | Groupe du domaine     | lecture              |

</div>

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

Les permissions sont présentées sur ce tableau :

<div align="center">

| Groupes                | Rôles                 | Droit                |                      
|------------------------|-----------------------|----------------------|
| Administrateurs        | Admis du serveur      | Contrôle total       | 
| SYSTEM                 | Windows/GPO/Services  | Contrôle total       | 
| CREATEUR PROPRIETE     | Gestion automatique   | par défaut           | 
| Utilisateurs           | Compte locaux/domaine | lecture et exécution |                     
| domaine computers      | PC du domaine         | lecture et exécution |
| DLG_RH                 | Groupe du domaine     | lecture              |

</div>

Activation de l'héritage :

<p align="center">

<img src="heritage/01.png" width="400">

<img src="heritage/02.png" width="400">

<img src="heritage/03.png" width="400">

<img src="heritage/04.png" width="400">

</p>


Permission :

<p align="center">

<img src="permission_NTFS/01.png" width="400">

<img src="permission_NTFS/02.png" width="400">

<img src="permission_NTFS/03.png" width="400">

<img src="permission_NTFS/04.png" width="400">

<img src="permission_NTFS/05.png" width="400">

<img src="permission_NTFS/06.png" width="400">

</p>


### 4. Vérification automatique des habilitations à partir de PowerShell

Vérification des droits de partages :

<p align="center">

<img src="powershell/01.png" width="400">

</p>

Vérification des permissions NTFS :

<p align="center">

<img src="powershell/02.png" width="400">

</p>

Vérification de l'héritage :

<p align="center">

<img src="powershell/03.png" width="400">

</p>


### 5. Tester l'accès réellement

Ce teste consiste à se connecter avec un utilisateur du domaine et essayer d’ouvrir le fichier depuis ce compte.

<p align="center">

<img src="connexion/01.png" width="400">

<img src="connexion/02.png" width="400">

<img src="connexion/03.png" width="400">

<img src="connexion/04.png" width="400">

<img src="connexion/05.png" width="400">

<img src="connexion/06.png" width="400">

<img src="connexion/07.png" width="400">

</p>

---

## VII. Conclusion

<p>La mise en place d’un dossier partagé sécurisé au sein d’un domaine Active Directory a permis de structurer et de fiabiliser la gestion des habilitations au sein de l’organisation. L’ensemble des étapes réalisées : création du domaine, organisation des unités d’organisation, définition des groupes de sécurité, configuration des permissions SMB et NTFS, puis automatisation du contrôle via un script PowerShell constitue une solution complète, conforme aux bonnes pratiques de gestion des accès.</p>

<p>Ce projet démontre l’importance d’une architecture d’habilitation claire et maîtrisée. Grâce à l’utilisation de groupes globaux et de groupes locaux de domaine, les droits d’accès sont désormais attribués de manière cohérente, évolutive et conforme au principe du moindre privilège. L’automatisation du contrôle des permissions via PowerShell renforce encore la sécurité en permettant de détecter rapidement toute dérive ou anomalie dans les droits attribués.</p>

<p>Les tests réalisés avec un utilisateur RH confirment le bon fonctionnement de l’ensemble du dispositif : les accès sont correctement restreints, les permissions appliquées sont conformes aux attentes, et le dossier partagé répond aux exigences de confidentialité propres au service.</p>

<p>En définitive, ce projet apporte une réponse efficace à la problématique initiale : il garantit une gestion fiable, sécurisée et automatisée des droits d’accès, tout en facilitant le travail des administrateurs et en renforçant la sécurité du système d’information. Cette démarche s’inscrit pleinement dans les standards professionnels de cybersécurité et constitue une base solide pour la gestion future des habilitations au sein de l’entreprise.</p>
