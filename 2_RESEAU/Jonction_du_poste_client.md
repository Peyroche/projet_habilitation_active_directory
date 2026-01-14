# JONCTION POSTES CLIENTS AU DOMAINE

---

## Objectif :

Cette fiche a pour objectif d'expliquer comment intégrer les postes clients dans un domaine afin qu’il soit géré, sécurisé et administré de manière centralisée par le serveur. Seul un administrateur du domaine disposant des droits nécessaires peut intégrer un poste au domaine. 

---

## Procédure jonction des postes clients au domaine :

La procédure utilisée est la suivante :

1. Se connecter à Windows server 22

2. Dans le gestionnaire de fichier, clic droit sur PC 

2. Cliquer sur propriété 

3. Ensuite cliquer sur renommer ce PC

4. Modifier

5. Entrer un domaine : mdf.corp 

6. Fournir :

- Un compte admin du domaine (ex : Administrateur)

- Mot de passe du domaine

7. Redémarrer le poste client.

---

## Démonstration jonction d'un poste client PC_RH Windows 10 au domaine :

<p align="center">

<img src="images_6/images_jonct/01.png" width="350">

<img src="images_6/images_jonct/02.png" width="350">

<img src="images_6/images_jonct/03.png" width="350">

<img src="images_6/images_jonct/04.png" width="350">

<img src="images_6/images_jonct/05.png" width="350">

<img src="images_6/images_jonct/06.png" width="350">

<img src="images_6/images_jonct/07.png" width="350">

<img src="images_6/images_jonct/08.png" width="350">

<img src="images_6/images_jonct/09.png" width="350">

<img src="images_6/images_jonct/10.png" width="350">

<img src="images_6/images_jonct/11.png" width="350">

<img src="images_6/images_jonct/12.png" width="350">

<img src="images_6/images_jonct/13.png" width="350">

</p>

---

## Authentification utilisateur_RH au domaine sur un poste client PC_RH Windows 10 :

Avant même que l’utilisateur_RH ne tape son mot de passe, le poste effectue une authentification machine auprès du contrôleur de domaine. Le PC utilise son compte ordinateur (créé dans AD lors de la jonction). Il prouve son identité grâce à un mot de passe machine (géré automatiquement et changé tous les 30 jours).

Cette étape permet :

- d’appliquer les GPO ordinateur,

- de vérifier que la machine est autorisée dans le domaine,

- d’établir une communication sécurisée avec le DC.


Une fois l’écran de connexion affiché, l’utilisateur_RH entre :

- son identifiant du domaine,

- son mot de passe,

- et le poste contacte le DC pour valider ces informations.

Cette authentification permet :

- de charger les GPO utilisateur,

- d’appliquer les droits d’accès (partages, imprimantes, etc.),

- de créer ou charger le profil utilisateur.


<p align="center">

<img src="images_7/images_RH/01.png" width="350">

<img src="images_7/images_RH/02.png" width="350">

<img src="images_7/images_RH/03.png" width="350">

</p>

---

## Test de vérification des permissions NTFS du Dossier_RH avec l'utilisateur_RH :

Rappel des droits d'accès aux dossiers :

| Dossiers     | OU_Groupes | DLG     | Permissions NTFS                                                                     |
|--------------|------------|---------|--------------------------------------------------------------------------------------|
| Dossier_RH   | DLG        | DLG_RH  | Change (Modification) : Lecture + modification, suppression, création de fichiers.   | 
| Dossier_INF  | DLG        | DLG_INF | Read (Lecture) : L’utilisateur peut lire, ouvrir, lister les fichiers.               |
| Dossier_CP   | DLG        | DLG_CP  | Read (Lecture) : L’utilisateur peut lire, ouvrir, lister les fichiers.               |


<p align="center">

<img src="images_8/images_NTFS_RH/01.png" width="350">

<img src="images_8/images_NTFS_RH/02.png" width="350">

<img src="images_8/images_NTFS_RH/03.png" width="350">

<img src="images_8/images_NTFS_RH/04.png" width="350">

<img src="images_8/images_NTFS_RH/05.png" width="350">

<img src="images_8/images_NTFS_RH/06.png" width="350">

<img src="images_8/images_NTFS_RH/07.png" width="350">

<img src="images_8/images_NTFS_RH/08.png" width="350">

</p>