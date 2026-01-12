# VERIFICATION DES ACCES ET PERMISSIONS NTFS

---

## Objectifs :

Vérifier que :
- Les utilisateurs peuvent accéder aux ressources selon les droits de partage SMB définis.
- Les permissions NTFS appliquées sur le dossier partage correspondent aux règles prévues.

---

## Procédure :

La procédure utilisée est la suivante : 

1. Depuis le poste client, ouvrir l’explorateur de fichiers.

2. Dans la barre d’adresse, saisir : \10.0.0.10\

3. Accès aux partages

4. Vérifier les permissions.

| Dossiers     | GG           | Permissions NTFS                                                                     |
|--------------|--------------|--------------------------------------------------------------------------------------|
| Dossier_RH   | DLG_RH       | Change (Modification) : Lecture + modification, suppression, création de fichiers.   | 
| Dossier_INF  | DLG_INF      | Read (Lecture) : L’utilisateur peut lire, ouvrir, lister les fichiers.               |
| Dossier_CP   | DLG_CP       | Read (Lecture) : L’utilisateur peut lire, ouvrir, lister les fichiers.               |

---

## Démonstrations :

- Vérification accès et permissions NTFS au Dossier_RH

<p align="center">

<img src="images/images_NTFS_RH/01.png" width="400">

<img src="images/images_NTFS_RH/02.png" width="400">

<img src="images/images_NTFS_RH/03.png" width="400">

<img src="images/images_NTFS_RH/04.png" width="400">

</p>


- Vérification accès et permissions NTFS au Dossier_INF

<p align="center">

<img src="images/images_NTFS_INF/01.png" width="400">

<img src="images/images_NTFS_INF/02.png" width="400">

<img src="image/images_NTFS_INF/03.png" width="400">

</p>


- Vérification accès et permissions NTFS au Dossier_CP

<p align="center">

<img src="images/images_NTFS_CP/01.png" width="400">

<img src="images/images_NTFS_CP/02.png" width="400">

<img src="images/images_NTFS_CP/03.png" width="400">

</p>



