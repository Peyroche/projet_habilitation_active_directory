# CREATION GG ET DLG

---

## Objectifs :

Créer des Groupes Globaux (GG) qui serviront à regrouper les utilisateurs selon leur service afin d’appliquer ensuite le modèle AGDLP. 

| Services              | OU_Groupes  | GG         | OU_Utilisateurs | Utilisateur  |
|-----------------------|-------------|------------|-----------------|--------------|
| Ressources Humaines   | GG          | GG_RH      | Utilisateur_RH  |  Placide     |
| Informatique          | GG          | GG_INF     | Utilisateur_INF |  Fortuné     |
| Comptabilité          | GG          | GG_CP      | Utilisateur_CP  |  Hugues      |

Créer des Groupes Domaines Local (DLG) qui seront utilisés pour attribuer des permissions NTFS/SMB sur les dossiers partagés du serveur. 

| Services              | OU_Groupes | DLG       |
|-----------------------|------------|-----------|
| Ressources Humaines   | DLG        | DLG_RH    |
| Informatique          | DLG        | DLG_INF   |
| Comptabilité          | DLG        | DLG_CP    |

---

## Procédure création des GG :

Pour la création des GG, la procédure utilisée est la suivante  :

1. Aller dans : OU_Groupes → GG 

2. Clic droit → Nouveau → Groupe 

3. Renseigner : 

- Nom du Groupe Global (ex : GG_RH) 

- Portée : Global 

- Type : Sécurité 

4. Valider. 

---

## Démonstration :

Pour la démonstration, nous nous servirons d'un seul exemple.

<p align="center">

<img src="images/images_GG_RH/01.png" width="400">

<img src="image/images_GG_RH/02.png" width="400">

<img src="images/images_GG_RH/03.png" width="400">

</p>

---

## Procédure création des DLG :

Pour la création des DLG, la procédure utilisée est la suivante  :

1. Aller dans : OU_Groupes → DLG 

2. Clic droit → Nouveau → Groupe 

3. Renseigner : 

- Nom du Groupe Global (ex : DLG_RH) 

- Portée : Local de domaine

- Type : Sécurité 

4. Valider. 

---

## Démonstration :

Pour la création des DLG, la procédure utilisée est la suivante  :

<p align="center">

<img src="images/images_DLG_RH/01.png" width="400">

<img src="images/images_DLG_RH/02.png" width="400">

<img src="images/images_DLG_RH/03.png" width="400">

</p>

---

## Procédure de l'ajout des utilisateurs au GG :

Pour l'ajout des utilisateurs au GG, la procédure utilisée est la suivante :

1. Aller dans l’OU contenant l’utilisateur (ex : Utilisateur_RH) 

2. Clic droit sur l’utilisateur (ex : Placide) 

3. Sélectionner Ajouter au groupe 

4. Entrer le groupe global (ex : GG_RH) 

5. Valider.

---

## Démonstration :

Pour la création des DLG, la procédure utilisée est la suivante  :

<p align="center">

<img src="images/images_ajout_RH/01.png" width="400">

<img src="images/images_ajout_RH/02.png" width="400">

</p>

---

## Procédure de l'ajout des GG aux DLG :

Pour l'ajout des GG aux DLG, la procédure utilisée est la suivante :

1. Aller dans : OU_Groupes → GG 

2. Clic droit sur le groupe global (ex : GG_RH)
 
3. Sélectionner Ajouter au groupe 

4. Entrer le Groupe Domaine Local (ex : DLG_RH) 

5. Valider.

---

## Démonstration :

Pour la création des DLG, la procédure utilisée est la suivante  :

<p align="center">

<img src="images/images_ajout_GG_RH/01.png" width="400">

<img src="images/images_ajout_GG_RH/02.png" width="400">

</p>

















