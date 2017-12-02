# Installation du VPN Étudiants Lille 1

## Fichiers de configuration

Quelque soit le système d'exploitation utilisé, les fichiers de configuration sont les mêmes. Ils sont disponibles ici même ou dans une archive nommée `50937_VPN_ETU_Config_Linuxv2.zip` disponible surle site du [Centre de Ressources Informatique](http://cri.univ-lille1.fr/Services-proposes/reseau/VPN-etudiant) de l'Université.

Les documentations données ici sont rédigés et donc valide le 1er décembre 2017.

## Linux

### Ubuntu (version 17.10 a

 1. Installer le paquet `openvpn`

        sudo apt-get update
        sudo apt-get install openvpn

 2. Installer le paquet `network-manager-openvpn` pour avoir une interface graphique simplifiant l'utilisation

        sudo apt-get install network-manager-openvpn network-manager-openvpn

 3. Importer le fichier de configuration [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn):

    > Menu Système → Préférences → Connexions réseau → Onglet VPN → Importez la configuration 

### Debian (version testing aka `buster`)

 1. Installer le paquet `openvpn`

        sudo apt-get update
        sudo apt-get install openvpn

 2. Installer le paquet `network-manager-openvpn-gnome` pour avoir une interface graphique simplifiant l'utilisation

        sudo apt-get install network-manager-openvpn-gnome

 3. Importer le fichier de configuration [`LILLE1-ETU.ovpn`](LILLE1-ETU.ovpn):

    > Paramètres → Réseau → Connexions réseau → Onglet VPN → Importez la configuration 

## Windows

### Windows 7

#### Installation

 1. Vérifier le type de votre système d'exploitation :

    Dans les propriétés  de l'ordinateur (clic-droit dans le Menu démarrer sur ordinateur) relever le type du système d'exploitation : 32 ou 64 bits.

 2. Récupérer le client VPN :

    Connecter vous à l'url <https://openvpn.net/index.php/download/community-downloads.html> et télécharger l’exécutable correspondant à votre architecture (32 ou 64 bits).

 3. Installer le client VPN :

    1. Exécuter le fichier téléchargé en tant qu'administrateur (clic droit + menu local).
    2. Accepter d'installer le périphérique si demandé
    3. Le parefeu Windows demande su quel type de réseau (privé/public) activer le périphérique: Choisissez privé
 4. Configuration du client VPN :

    1. Désarchiver l'archive des fichiers de configuration (elle contient 3 fichiers : `openvpn_etu.ovpn`, `openvpn_etu.conf` et `Terena-chaine_autorites.perm`)
    2. Placer les fichiers dans le répertoire de configuration `C:\Program Files\OpenVPN\config` (Il s'agit d'un sous-répertoire du répertoire du programme, placé par défaut en `C:\Program Files` ou `C:\Program Files (x86)` selon le contexte).
    3. Faire en sorte que le programme s'exécute en tant qu'administrateur :

      1. Se rendre dans le dossier d'installation `C:\Program Files\OpenVPN\bin`
      2. Cliquer droit sur `openvpn.exe` et `openvpn-gui.exe`, choisir *Propriétés*, puis l'onglet *Compatibilité* et cocher la case *Executer ce programme en tant que Administrateur*.

    4. (*facultatif*) Configurer le service OpenVPN pour qu'il s'active automatiquement au démarrage du système (Si vous n'appliquez pas cette procédure, vous devrez démarrer manuellement le programme openvpn pour chaque session) :

      1. Panneau de configuration → Système et sécurité → Outils d'administration → Services
      2. Clic-droit sur le service *OpenVPNService* puis choisir comme type de démarrage *Automatique*

#### Connexion

**La connexion ne peut se faire qu'une fois que le programme openvpn est démarré**

 1. Localiser l'icône dans la barre des tâches
 2. Clic-droit sur l'icône et sélectionner *Connecter*
 3. Entrer ses identifiants Lille 1
 4. Si tout se passe bien l'icône passe au vert

#### Déconnexion

 1. Clic-droit sur l'icône dans la barre des tâches
 2. Sélectionner *Déconnecter*

------------------------------------------------------------------------------
