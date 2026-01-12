# ATTRIBUTIONS DES DROITS DE PARTAGE SMB

---

## Procédure :

Les droits de partage SMB s’appliquent au niveau du partage en suivant la procédure suivante :

1. Clic droit sur le dossier (ex : Dossier_RH)

2. Propriétés 

3. Onglet Partage 

4. Partage avancé 

5. Cocher Partager ce dossier 

6. Cliquer sur Autorisations 

7. Supprimer “Tout le monde” 

8. Ajouter le Groupe Domaine Local (ex : DLG_RH) 

9. Donner les droits associés au groupe. (ex : Full Control).


| Dossiers     | OU_Groupes  | DLG      | Droits de partage SMB                                                                |
|--------------|-------------|----------|--------------------------------------------------------------------------------------|
| Dossier_RH   | DLG         | DLG_RH   | Full Control (Contrôle total) : Modification + gestion des permissions du partage.   | 
| Dossier_INF  | DLG         | DLG_INF  | Change (Modification) : Lecture + modification, suppression, création de fichiers.   |
| Dossier_CP   | DLG         | DLG_CP   | Read (Lecture) : L’utilisateur peut lire, ouvrir, lister les fichiers.               |


---

## Démonstrations :

- Permissions SMB du Dossier_RH

<p align="center">

<img src="images/images_SMB_RH/01.png" width="400">

<img src="images/images_SMB_RH/02.png" width="400">

<img src="images/images_SMB_RH/03.png" width="400">

<img src="images/images_SMB_RH/04.png" width="400">

<img src="images/images_SMB_RH/05.png" width="400">

<img src="images/images_SMB_RH/06.png" width="400">

<img src="images/images_SMB_RH/07.png" width="400">

<img src="images/images_SMB_RH/08.png" width="400">

<img src="images/images_SMB_RH/09.png" width="400">

<img src="images/images_SMB_RH/10.png" width="400">

</p>


- Permissions SMB du Dossier_INF

<p align="center">

<img src="images/images_SMB_INF/01.png" width="400">

<img src="images/images_SMB_INF/02.png" width="400">

<img src="images/images_SMB_INF/03.png" width="400">

<img src="images/images_SMB_INF/04.png" width="400">

<img src="images/images_SMB_INF/05.png" width="400">

<img src="images/images_SMB_INF/06.png" width="400">

<img src="images/images_SMB_INF/07.png" width="400">

<img src="images/images_SMB_INF/08.png" width="400">

<img src="images/images_SMB_INF/09.png" width="400">

<img src="images/images_SMB_INF/10.png" width="400">

</p>


- Permissions SMB du Dossier_CP

<p align="center">

<img src="images/images_SMB_CP/01.png" width="400">

<img src="images/images_SMB_CP/02.png" width="400">

<img src="images/images_SMB_CP/03.png" width="400">

<img src="images/images_SMB_CP/04.png" width="400">

<img src="images/images_SMB_CP/05.png" width="400">

<img src="images/images_SMB_CP/06.png" width="400">

<img src="images/images_SMB_CP/07.png" width="400">

<img src="images/images_SMB_CP/08.png" width="400">

<img src="images/images_SMB_CP/09.png" width="400">

</p>