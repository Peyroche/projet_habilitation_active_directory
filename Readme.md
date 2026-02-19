## PROJET 2 : HABILITATION SUR UN DOSSIER PARTAGE

---

## I. Introduction 

<p>Dans un environnement professionnel, la gestion des droits d’accès aux ressources est un élément essentiel de la sécurité informatique. Les entreprises doivent garantir que chaque collaborateur accède uniquement aux informations nécessaires à l’exercice de ses fonctions.</p>
<p>Ce projet consiste à mettre en place un dossier partagé au sein d’un domaine Active Directory, à définir des niveaux d’habilitation adaptés aux différents services, puis à vérifier automatiquement la conformité de ces droits grâce à un script PowerShell.</p>

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

## IV. Enjeux

<p><b>1. Sécurité :</b></p>
<p>Assurer que chaque collaborateur accède uniquement aux ressources nécessaires à ses missions.</p>
<p>Limiter les risques de fuite de données ou de compromission.</p>

<p><b>2. Organisation :</b></p>
<p>Structurer les habilitations selon les services, les rôles et les responsabilités</p>
<p>Faciliter les mouvements internes (mobilité, arrivée, départ).</p>

<p><b>3. Opérationnel :</b></p>
<p>Automatiser les contrôles pour réduire les erreurs humaines</p>
<p>Optimiser le travail des administrateurs système.</p>

<p><b>4. Traçabilité :</b></p>
<p>Conserver une vision claire, documentée et vérifiable des droits d’accès</p>
<p>Détecter rapidement les anomalies ou dérives d’habilitation.</p>

<p><b>5. Conformité :</b></p>
<p>Répondre aux bonnes pratiques de cybersécurité (ANSSI, RGPD, ISO 27001)</p>
<p>Pouvoir justifier des droits attribués lors d’un audit.</p>

---

## V. Contexte d'intervention

<p>Dans le cadre de la gestion des habilitations dossier partage, une procédure d'intervention a été réalisée :</p>

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

## VI. Réalisations 

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

### Ajout d’un poste client Windows 10 Entreprise au domaine

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

| Dossier              | Secteur              | OU_DLG           |                          
|----------------------|----------------------|------------------|
| Dossier_RH           | RH                   | DLG_RH           | 


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

---

## VII. Conclusion

<p>La mise en place d’un dossier partagé sécurisé au sein d’un domaine Active Directory a permis de structurer et de fiabiliser la gestion des habilitations au sein de l’organisation. L’ensemble des étapes réalisées : création du domaine, organisation des unités d’organisation, définition des groupes de sécurité, configuration des permissions SMB et NTFS, puis automatisation du contrôle via un script PowerShell constitue une solution complète, conforme aux bonnes pratiques de gestion des accès.</p>

<p>Ce projet démontre l’importance d’une architecture d’habilitation claire et maîtrisée. Grâce à l’utilisation de groupes globaux et de groupes locaux de domaine, les droits d’accès sont désormais attribués de manière cohérente, évolutive et conforme au principe du moindre privilège. L’automatisation du contrôle des permissions via PowerShell renforce encore la sécurité en permettant de détecter rapidement toute dérive ou anomalie dans les droits attribués.</p>

<p>Les tests réalisés avec un utilisateur RH confirment le bon fonctionnement de l’ensemble du dispositif : les accès sont correctement restreints, les permissions appliquées sont conformes aux attentes, et le dossier partagé répond aux exigences de confidentialité propres au service.</p>

<p>En définitive, ce projet apporte une réponse efficace à la problématique initiale : il garantit une gestion fiable, sécurisée et automatisée des droits d’accès, tout en facilitant le travail des administrateurs et en renforçant la sécurité du système d’information. Cette démarche s’inscrit pleinement dans les standards professionnels de cybersécurité et constitue une base solide pour la gestion future des habilitations au sein de l’entreprise.</p>
