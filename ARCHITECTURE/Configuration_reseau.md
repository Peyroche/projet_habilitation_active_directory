# Configuration du réseau  

---

## Procédure configuration du réseau :

La procédure de configuration du réseau est la suivante :

1. Accéder au panneau de configuration

2. Cliquer sur Réseau et Internet

3. Cliquer sur centre de partage et réseau

4. Cliquer sur Ethernet

5. Choisir Propriétés

6. Dans la liste, sélectionner : Protocole Internet version 4 (TCP/IPv4)

7. Configurer le réseau. 

| Machines               | IP         |  Masque       |  Passerelle    | Serveur DNS préféré |
|------------------------|------------|---------------|----------------|---------------------|
| Poste client (PC)      | 10.0.0.20  | 255.255.255.0 |      /         |   10.0.0.10         | 
| Serveur Windows Server | 10.0.0.10  | 255.255.255.0 |       /        |   10.0.0.10         |                     

---

## Démonstrations :

- Configuration du réseau sur le Serveur Windows Server, effectuée par l'administrateur

<p align="center">

<img src="images/images_conf_admin/01.png" width="400">

<img src="images/images_conf_admin/02.png" width="400">

<img src="images/images_conf_admin/03.png" width="400">

<img src="images/images_conf_admin/04.png" width="400">

<img src="images/images_conf_admin/05.png" width="400">

<img src="images/images_conf_admin/06.png" width="400">

<img src="images/images_conf_admin/07.png" width="400">

<img src="images/images_conf_admin/08.png" width="400">

<img src="images/images_conf_admin/09.png" width="400">

<img src="images/images_conf_admin/10.png" width="400">

</p>


- Configuration du réseau sur le poste client, effectuée par l'utilisateur_RH du nom de Placide

<p align="center">

<img src="images/images_conf_user/01.png" width="400">

<img src="images/images_conf_user/02.png" width="400">

<img src="images/images_conf_user/03.png" width="400">

<img src="images/images_conf_user/04.png" width="400">

<img src="images/images_conf_user/05.png" width="400">

<img src="images/images_conf_user/06.png" width="400">

<img src="images/images_conf_user/07.png" width="400">

<img src="images/images_conf_user/08.png" width="400">

<img src="images/images_conf_user/09.png" width="400">

<img src="images/images_conf_user/10.png" width="400">

</p>

---

## Activation de la carte réseau :

Pour activer la carte réseau, la procédure est la suivante :

1. Sur VirtualBox → Paramètres de la VM client 

2. Onglet Réseau 

3. Coche la case "Activer l’interface réseau" 

4. Vérifie que : 

- Mode d’accès réseau = Réseau interne 

- Nom = le même que sur le serveur (ex : intnet) 

- Type d’interface = Intel PRO/1000 MT Desktop (82540EM)

- Câble branché = coché ✅ 

---

## Démonstrations :

- Activation carte réseau sur Serveur Windows server

<p align="center">

<img src="images/images_carte/01.png" width="400">

<img src="images/images_carte/02.png" width="400">

</p>


- Activation carte réseau sur le poste client

<p align="center">

<img src="images/images_carte/03.png" width="400">

<img src="images/images_carte/04.png" width="400">

</p>

---

## Vérification de la configuration réseau du poste client :

On vérifie la configuration réseau du poste client dans l'invite de commande avec :
 
1. ipconfig : 
- Pour confirmer que le poste client a une adresse IP dans le même réseau que le serveur
- Pour Vérifier que le DNS pointe vers le contrôleur de domaine.

2. Ping 10.0.0.10 :
- Pour vérifier que le poste client peut joindre le serveur
- Pour confirmer que les deux machines sont dans le même réseau VirtualBox
- pour s’assurer que le serveur est allumé et que le pare‑feu ne bloque pas ICMP.

---

## Démonstrations :

<p align="center">

<img src="images/images_verifica/01.png" width="400">

</p>


