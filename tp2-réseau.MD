# B1 Réseau 2018 - TP2
Thomas DUMONT - 11/12/2018

## I - Exploration locale en solo
### 1. Affichage d'informations sur la pile TCP/IP locale
* **Affichez les infos des cartes réseau de votre PC :**
    * Interface Wifi : 
        * Nom : Carte réseau sans fil Wi-Fi
        * Adresse MAC : F8-59-71-94-D5-5E
        * Adresse IP : 10.33.1.163
        * Adresse de réseau : 10.33.0.0
        * Adresse de broadcast : 10.33.3.255

    * Interface Ethernet : 
        * Nom : Carte Ethernet Ethernet	
        * Adresse MAC : 54-E1-AD-4b-24-C0
        * Adresse IP : \
        * Adresse de réseau : \
        * Adresse de broadcast : \

* **Affichez votre gateway :**

Ecrire la commande « ipconfig », ensuite aller dans les informations de sa carte réseau sans fil Wi-Fi et l’adresse IP de la passerelle de la carte Wi-Fi sera affiché après « Passerelle par défaut ».
    
* **Trouvez comment afficher les informations sur une carte IP :**

Cliquer droit sur l’icone Wi-Fi dans la barre des tâches, cliquer sur « ouvrir les paramètres réseaux et internet », cliquer sur « Afficher vos propriétés réseau » et les informations concernant pour l’interface Wi-Fi seront affichés.
    
* **A quoi sert la gateway dans le réseau d’Ingésup ?**

Elle permet aux élèves de les connecter au réseau internet grâce à une machine installé au sein de l’établissement d’Ynov qui est connecté au même réseau que les élèves.

### 2. Modifications des informations
#### A. Modifications d'adresse IP - pt. 1

* **Calculez la première et dernière adresse IP disponibles du réseau :**

Pour la première adresse IP disponible on prend l'adresse réseau et on rajoute 1 à la fin car elle est déjà utilisé. On obtient alors : 10.33.0.1.
Et pour la dernière adresse disponible on prend l'adresse de broadcast et on enlève 2 à la fin car la dernière adresse IP est déjà utilisée pour le broadcast et l'avant dernière IP est utilisée pour la gateway. On obtient alors : 10.33.3.253.

* **Changez l'adresse IP de votre carte WiFi pour une autre :**

Pour changer l'adresse IP manuellement il faut suivre cette procédure :

Panneau de configuration, Réseau et internet, Centre réseau et partage, Modifier les paramètres de la carte, clique droit sur la carte réseau Wi-Fi, propriétés, clique sur "Internet Protocol Version 4 (TCP/IPv4)", propriétés, cocher "Utiliser l'adresse IP suivante :"
Ensuite remplir la case "adresse IP :" en prenant les 3 séries de chiffre qu'avait nos adresse IP initial, donc 10.33.1 et terminé par un nombre autre que celui qu'on avait, par exemple : 10.33.1.33
Remplir la case "Masque de sous-réseau :" par 255.255.255.0.

### C. Modification d'adresse IP - pt. 2


## II. Exploration locale en duo
### 1. Prérequis

Tout d'abord nous avons retiré les pare-feux

### 2. Câblage

Nous avons procédé au câblage entre les deux machines grâce à un câble RJ45

### 3. Modification d'adresse IP

*  Modifiez l'IP des deux machines pour qu'elles soient dans le même réseau : 

Aller dans : Panneau de configuration > Réseau et Internet > Connexions réseau > clic droit sur "Ethernet" puis clic sur "Propriété" > clic sur "Internet Protocol Version 4" puis clic sur Propriétés.

Pour le PC_1 nous avons mis l'adresse IP suivante : 192.168.0.1 et pour le PC_2 192.168.0.2 .
Pour le masque de sous-réseau nous avons mis : 255.255.255.0 .

* Vérifiez à l'aide de commandes que vos changements ont pris effet :

Pour cela il suffit d'aller dans le terminal et d'y inscrire "ip config" (sous windows)!

* Utilisez ping pour tester la connectivité entre les deux machines :

Dans cette partie il suffit d'écrire dans le terminal "ping {adresse ip de l'ordinateur connecté}" soit ici "ping 192.168.0.2" et nous pouvons observer que le pc nous confirme bien le test de 4 paquets.

### 4. Utilisation d'un des deux comme gateway

* Sur le PC qui n'a plus internet, sur la carte Ethernet, définir comme passerelle l'adresse IP de l'autre PC :
