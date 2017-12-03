# Description du VPN

## Présentation 

Le VPN, pour *Virtual Private Network* ou *Réseau Privé Virtuel* en français, permet d'avoir accès de façon transparente à des ressources hébergées sur le réseau interne d'un établissement (pour ce qui nous concerne de l'Université de Lille 1 et de son IUT) depuis n'importe quel ordinateur connecté à l'Internet. Il crée un tunnel chiffré entre l'ordinateur de l'utilisateur et le réseau de l'université donnant l'illusion de la connexion physique du poste au réseau de l'établissement.

Grâce à ce dispositif l'utilisateur pourra avoir accès depuis chez lui à différentes ressources informatiques du département informatique de l'IUT «A» (accès à l'environnement de TP, au serveur de bulletins de notes ou au serveur d'assistance par exemple) qui sinon ne seraient accessibles que depuis les salles de TP ou le réseau filaire du campus.

Les seules contraintes sont de devoir installer et configurer le logiciel permettant d'établir une connexion chiffrée entre son poste et le réseau privé de l'Université. Ce dispositif ne dispense pas d'une authentification si le service interrogé le demande.

Notez qu'il existe d'autres ressources de l'Université (comme [Moodle](http://moodle.univ-lille1.fr)) ou du département (comme le serveur [GitLab](http://git-iut.univ-lille1.fr) par exemple) qui ne demandent pas l'utilisation du VPN. La page d'[accueil des outils](https://accueil.iut-info.univ-lille1.fr) du département liste l'intégralité des services offerts et leur mode d'accès.

Par ailleurs, via le VPN, les machines des salles de TP du département informatique de l'IUT «A» sont accessibles en `ssh` en journée (de 8h à 20h) et la machine **`tp.iut-infobio.priv.univ-lille1.fr`** est accessible en permanence à tous les personnels et étudiants du département.

L'Université offre deux VPN séparés : un pour les **personnels** de l'Université et un autre pour les **étudiants**. Chacun permet d'accéder à des ressources différentes.

## Condition d'accès

L'accès au VPN n'est permis qu'après s'être authentifié une fois sur le [portail](http://portail.univ-lille1.fr) de l'établissement. Vous n'aurez donc accès à ce service qu'à l'issue de votre première connexion au portail et après l'avoir activé dans la rubrique <em>Mon compte</em> de celui-ci.

Par ailleurs à chaque connexion une authentification avec vos identifiants et mots de passe de l'Université (ceux utilisés pour l'accès au portail, Wifi ou email de l'Université) vous sera demandée.

**Les services de l'Université seront également très attentif à ce que votre poste soit parfaitement sécurisé. Système d'exploitation, anti-virus et outils utilisés doivent être à jour.**


# Installation du VPN

Le VPN utilisé par les services de l'Université est [OpenVPN](https://openvpn.net). Pour chaque système d'exploitation il est donc nécessaire d'installer les logiciels clients permettant de dialoguer avec ce serveur et de paramétrer ces outils avec les fichiers de configuration ad-hocs.

## Fichiers de configuration

Quelque soit le système d'exploitation utilisé, les fichiers de configuration sont les mêmes. Ils sont disponibles dans une archive disponible sur le site du Centre de Ressources Informatique pour les [personnels](http://cri.univ-lille1.fr/Services-proposes/reseau/vpn) ou les [étudiants](http://cri.univ-lille1.fr/Services-proposes/reseau/VPN-etudiant) de l'Université.

On en trouve ici une version simplifiée et vérifiée le **1er décembre 2017** :

 * [LILLE1.ovpn](LILLE1.ovpn) pour le réseau des personnels ;
 * [LILLE1-etu.ovpn](LILLE1-etu.ovpn) pour le réseau des étudiants.

Avvant de commencer il faut récupérer le fichier qui vous concerne.

## Installation en mode graphique

Un guide d'installation simplifié est donné ici pour différents systèmes d'exploitations.

### Ubuntu GNU/Linux (17.10)

Cette procédure a été testée et validée avec Ubuntu version 17.10 le 1er décembre 2017.

 1. Installer le paquet `openvpn`

        sudo apt-get update
        sudo apt-get install openvpn

 2. Installer le paquet `network-manager-openvpn-gnome` pour avoir une interface graphique simplifiant l'utilisation

        sudo apt-get install network-manager-openvpn-gnome

 3. Importer le fichier de configuration correspondant à votre statut ([`LILLE1.ovpn`](LILLE1.ovpn) ou [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn)) :

    > Menu Paramètres (cliquer en haut à gauche de l'écran) → Réseau → VPN → + → Importer depuis un fichier

 4. Saisir votre identifiant dans le champ *Nom d'utilisateur*

Pour démarrer une connexion il suffit alors de choisir *Se connecter* dans le sous-menu *VPN désactivé* du menu principal (cliquer en haut à gauche de l'écran) et de saisir votre mot de passe.

### Debian GNU/Linux (stretch, 9.x)

Cette procédure a été testée et validée avec Debian version stretch le 1er décembre 2017.

 1. Installer le paquet `openvpn`

        sudo apt-get update
        sudo apt-get install openvpn

 2. Installer le paquet `network-manager-openvpn-gnome` pour avoir une interface graphique simplifiant l'utilisation

        sudo apt-get install network-manager-openvpn-gnome

 3. Importer le fichier de configuration correspondant à votre statut ([`LILLE1.ovpn`](LILLE1.ovpn) ou [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn)) :

    * avec l'environnement MATE

      > Menu Système → Préférences → Internet et réseau → Connexions réseau → Add → Import a saved VPN configuration

    * avec l'environnement GNOME

      > Menu Paramètres → Réseau → + → Importer depuis un fichier

 4. Saisir votre identifiant dans le champ *Nom d'utilisateur*

Pour démarrer une connexion il suffit alors de choisir *Se connecter* dans le sous-menu *VPN désactivé* du menu principal (cliquer en haut à gauche de l'écran) et de saisir votre mot de passe.

### Mac OS X (High Sierra, 10.13.1)

Cette procédure a été testée et validée avec Mac OS X High Sierra le 1er décembre 2017.

 1. Installer l'application [Tunnelblick](https://tunnelblick.net).
 
 2. Démarrer l'application Tunnelblick.
 
 3. Importer le fichier de configuration correspondant à votre statut ([`LILLE1.ovpn`](LILLE1.ovpn) ou [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn)) en le glissant sur l'icône Tunnelblick présente dans la barre de menu (en haut à droite de l'écran).

Pour démarrer une connexion il suffit alors de :

 1. démarrer TunnelBlick (si ça n'est pas déjà fait) ;
 2. de choisir le réseau de son choix dans le menu de l'application dans la barre de ;
 3. de saisir votre nom d'utilisateur et mot de passe.

### Windows (10 pro)

Cette procédure a été testée et validée avec Windows 10 Professionnel le 1er décembre 2017.

 1. Récupérer le client VPN à l'URL <https://openvpn.net/index.php/open-source/downloads.html> en téléchargeant l’installateur pour Windows [openvpn-install-2.4.4-I601.exe](https://swupdate.openvpn.org/community/releases/openvpn-install-2.4.4-I601.exe).

 2. Installer le client VPN :

    1. Exécuter le fichier téléchargé.
    2. Accepter d'installer le périphérique si cela est demandé.

 3. Configurer le client VPN

    1. Démarrer le programme *OpenVPN GUI* ;
    2. Cliquer droit sur l'icône de *OpenVPN GUI* dans la barre de tâches puis choisissez *Import file...* pour importer le fichier de configuration correspondant à votre statut ([`LILLE1.ovpn`](LILLE1.ovpn) ou [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn)) :


Pour démarrer une connexion il suffit alors :

 1. de démarrer *OpenVPN GUI* (si ça n'est pas déjà fait) ;
 2. d'accéder au menu du programme en cliquant avec le bouton de droite de la souris sur l'icône *OpenVPN GUI* dans la barre des tâches ;
 3. de choisir *Connecter* ;
 4. de saisir votre nom d'utilisateur et mot de passe.

## Utilisationn en ligne de commande

Sous Linux on peut également, après avoir installé `openvpn`, il est possible de juste récupérer le script correspondant à votre statut ([`vpnlille1`](vpnlille1) pour les personnels et [`vpnetu`](vpnetu) pour les étudiants) et l'appeler en ligne de commande avec l'option `start` pour démarrer une connexion et l'option `stop` pour arrêter une connexion.
