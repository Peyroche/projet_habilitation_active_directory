# INTRODUCTION

---

Dans la gestion des habilitations au sein d’un domaine Active Directory, la création des groupes locaux de domaine (DLG) constitue une étape essentielle pour structurer et appliquer les droits d’accès aux différentes ressources du système d’information. Alors que les groupes globaux (GG) permettent de regrouper les utilisateurs selon leur rôle ou leur service, les groupes locaux de domaine ont pour fonction d’attribuer les permissions directement sur les ressources, qu’il s’agisse de dossiers partagés, d’imprimantes, de services ou d’applications internes.

La mise en place des DLG s’inscrit dans la continuité du modèle AGDLP, qui vise à organiser les habilitations de manière claire, évolutive et sécurisée. Dans ce modèle, les utilisateurs sont intégrés dans des groupes globaux, eux‑mêmes ajoutés aux groupes locaux de domaine, lesquels portent les droits effectifs sur les ressources. Cette séparation entre l’identité (GG) et les permissions (DLG) permet une administration plus simple, une meilleure traçabilité et une adaptation rapide en cas de changement organisationnel.

---

## Procédure création des DLG :

La procédure utilisée est la suivante  :

1. Aller dans : OU_Groupes → DLG 

2. Clic droit → Nouveau → Groupe 

3. Renseigner : 

- Nom du Groupe Global (ex : DLG_RH) 

- Portée : Local de domaine

- Type : Sécurité 

4. Valider. 

---

## Tableau récapitulatif :

| Services              | OU_Groupes | DLG       |
|-----------------------|------------|-----------|
| Ressources Humaines   | DLG        | DLG_RH    |
| Informatique          | DLG        | DLG_INF   |
| Comptabilité          | DLG        | DLG_CP    |

---

## Procédure ajout des GG aux DLG :

La procédure utilisée est la suivante :

1. Aller dans l’OU contenant l’utilisateur (ex : Utilisateur_RH) 

2. Clic droit sur l’utilisateur (ex : Placide) 

3. Sélectionner Ajouter au groupe 

4. Entrer le groupe global (ex : GG_RH) 

5. Valider.

---

## Tableau récapitulatif :

| Services              | OU_Groupes   | OU_Utilisateurs   | Utilisateurs |
|-----------------------|--------------|-------------------|--------------|
| Ressources Humaines   | GG_RH        | Utilisateur_RH    |  Placide     |
| Informatique          | GG_INF       | Utilisateur_INF   |  Fortuné     |
| Comptabilité          | GG_CP        | Utilisateur_CP    |  Hugues      |

