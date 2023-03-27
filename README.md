# Projet Infrastructure 
# ( EN COURS DE MODIFICATION... )
# ( Les screenshots seront repostés prochainement ;-) )
# ( Le projet sera également modifié pour une utilisation avec VMWare ) <br><br><br>

## Partie 1 : Installation d'une machine virtuelle et de serveurs

### Déployer une machine virtuelle Linux Server (sans interface)

Cette section est librement inspirée du document [`Administration de site web`](https://docs.google.com/document/d/15ky8SdX2-H7chityNs0wYTlIuz7jJA-hsECiCAqkCr8/edit) de Marc GONZALEZ.

#### Installation de VirtualBox

Allez sur le site de [VirtualBox](https://www.virtualbox.org/).

Sur la page d'accueil, cliquez sur le bouton `Download VirtualBox X.X`.

![page d'accueil de VirtualBox](images/S6iiFo9nRL.png)

Téléchargez et installez VirtualBox pour Windows (ne fermez pas la fenêtre du navigateur).

![Lien vers VirtualBox pour Windows](images/xYVh0QU67d.png)

Faites défiler la page précédente, téléchargez et installez `VirtualBox X.X.XX Oracle VM VirtualBox Extension Pack`.

![Lien vers VirtualBox 6.1.26 Oracle VM VirtualBox Extension Pack](images/cS30n5iX8u.png)

#### Configuration de VirtualBox

Exécutez VirtualBox.

Cliquez sur le bouton `Nouvelle` (ou sur le menu `Machine -> Nouvelle…` (`CTRL+N`)).

![VirtualBox icone Nouvelle](images/hc6Ne5e49x.png)

Dans la boîte de dialogue `Nom et système d'exploitation`, donnez un nom à la nouvelle machine virtuelle (exemple : `debian`), sélectionnez un répertoire de destination, choisissez le type `Linux` et la version `Debian (64-bit)` puis cliquez sur le bouton `Suivant`.

![boîte de dialogue Nom et système d'exploitation](images/J4tQbfanDE.png)

Dans la boîte de dialogue `Taille de la mémoire`, sélectionnez si possible `2048` en RAM puis cliquez sur le bouton `Suivant`.

![boîte de dialogue Taille de la mémoire](images/kBIrk0eu0L.png)

Dans la boîte de dialogue `Disque dur`, sélectionnez l'option par défaut `Créer un disque dur virtuel maintenant` puis cliquez sur le bouton `Suivant`.

![boîte de dialogue Disque dur](images/0dEbxaPYV6.png)

Dans la boîte de dialogue `Type de fichier de disque dur`, sélectionnez l'option par défaut `VDI (VirtualBox Disk Image)` puis cliquez sur le bouton `Suivant`.

![boîte de dialogue Type de fichier de disque dur](images/8VJEG8GdRp.png)

Dans la boîte de dialogue `Stockage sur disque dur physique`, sélectionnez l'option par défaut `Dynamiquement alloué` puis cliquez sur le bouton `Suivant`.

![boîte de dialogue Stockage sur disque dur physique](images/gNhbXkCdOb.png)

Dans la boîte de dialogue `Emplacement du fichier et taille`, laissez le chemin par défaut mais saisissez si possible `20,00` Go en taille du disque virtuel puis cliquez sur le bouton `Créer`.

![boîte de dialogue Emplacement du fichier et taille](images/3nBMEo6oBR.png)

Une nouvelle machine virtuelle apparaît sur l'écran principal de VirtualBox. Sélectionnez cette machine virtuelle et cliquez sur le bouton `Configuration`.

![Ecran principal de VirtualBox et bouton Configuration](images/3Y7d9MlsGx.png)

Dans la section `Système`, onglet `Processeur`, saisissez `2` dans le champ `Nombre de processeurs` et cochez dans les `Fonctions avancées` les options `Activer PAE/NX` et `Activer VT-x/ADM-Vimbriqué` (si disponible).

![Configuration, section Système, onglet Processeur](images/Dl3cWJysSO.png)

Dans la section `Réseau`, onglet `Adapter1`, sélectionnez l'option `Accès par pont` dans le `Mode d'accès réseau`. Cliquez ensuite sur le bouton `OK`.

**Remarque :** L'option `Accès par pont` ne fonctionne pas sur le réseau du CESI.

![Configuration, section Réseau, onglet Adapter1](images/GeF1kLE2dP.png)

#### Téléchargement d'une image Debian

Récupérez l'image de la dernière version de la distribution Debian sur le site [debian.org](https://www.debian.org/).

![Site debian.org](images/Hi1KvZBDyE.png)

#### Sélection de l'image Debian

Dans la section `Stockage`, sur l'option `Controller IDE`, cliquez sur l'icône `Ajoute un lecteur optique.`.

![Configuration, section Réseau, onglet Adapter1](images/DABwAFjRGA.png)

Dans la boîte de dialogue `nom_machine_virtuelle - Optical Disk Selector`, cliquez sur le bouton `Ajouter`.

![boîte de dialogue nom_machine_virtuelle - Optical Disk Selector](images/VkpLaQqFAb.png)

Dans la boîte de dialogue `Choisissez un fichier de disque optique virtuel`, parcourez votre ordinateur et sélectionnez l'image de Debian puis cliquez sur le bouton `Ouvrir`.

![boîte de dialogue Choisissez un fichier de disque optique virtuel](images/h6L1g24gWI.png)

Dans la boîte de dialogue `nom_machine_virtuelle - Optical Disk Selector`, sélectionnez l'image disque de Debian et cliquez sur le bouton `Choisir`.

Fermez la boite de dialogue `Paramètres` en cliquant sur le bouton `OK`.

#### Installation de Debian

Sur l'écran principal de VirtualBox, sélectionnez la machine virtuelle et cliquez sur le bouton `Démarrer`.

Lors de l'installation de Debian, utilisez les flèches du clavier pour effectuer une sélection, la touche `ESPACE` pour cocher une option et la touche `ENTREE` pour valider.

Sélectionnez l'option `Install`.

**Très important !** Sélectionnez l'option `Install` et surtout pas l'option `Graphical Install`.

![option install](images/lLTwVS3Nxo.png)

Sélectionnez la langue utilisée lors de l'installation et validez.

**Remarque :** Il est préférable d'utiliser l'anglais pour faciliter la recherche lors de l'apparition de messages d'erreur.

![option langue de l'installation](images/EFzyd1ucqt.png)

Sélectionnez la time zone `United States`.

**Remarque :** Si vous ne trouvez pas le français, sélectionnez l'option `Other`, puis `Europe`, puis `France`. Cependant, un problème va se produire par la suite car le language anglais et la time zone française ne sont pas compatible.

![option time zone](images/YhbvHyUB5Z.png)

Sélectionnez le type de clavier `French`.

![option du clavier](images/Xll4WdA0kH.png)

Saisissez le nom de la machine virtuelle.

![option nom](images/I2a8lPEypk.png)

Saisissez le nom de domaine de la machine virtuelle.

![option nom de domaine](images/y5f5Bhrsen.png)

Saisissez le mot de passe du compte *root*.

**Attention !** Le compte *root* est l'administrateur principal de la machine. Il est très important de sécuriser ce mot de passe.

![option mot de passe root](images/v6oQ2A00IZ.png)

Saisissez à nouveau le mot de passe du compte *root*.

**Remarque :** Vous pouvez afficher les mots de passe en clair si vous cochez la case `Show Password in Clear`.

![option confirmation du mot de passe root](images/AuOWpA6paa.png)

Saisissez le nom complet du premier compte utilisateur.

![option nom complet de compte utilisateur](images/1KPAwe8ZJS.png)

Saisissez l'identifiant du premier compte utilisateur.

![option identifiant de compte utilisateur](images/mH75Bz04KY.png)

Saisissez le mot de passe du compte utilisateur.

![option mot de passe compte utilisateur](images/8d5e17FBiu.png)

Saisissez à nouveau le mot de passe du compte utilisateur.

![option confirmation du mot de passe compte utilisateur](images/VjWPnm4k47.png)

Sélectionnez la time zone de la machine (le choix n'est pas important et pourra être modifié par la suite).

![option time zone](images/6ZaelYh7kW.png)

Sélectionnez l'option `Guided - use entire disk` pour partitionner et utiliser l'intégralité de l'espace disque réservé lors de la configuration de la machine virtuelle.

![option partition de disques](images/wlMDh4TJUN.png)

Vérifiez que le disque correct est sélectionné.

![option sélection du disque à partitionner](images/6aMdRHj2ZM.png)

Sélectionnez l'option de partitionnement `All files in one partition (recommended for new users)`.

![option de partitionnement](images/lnlYleVuDu.png)

Vérifiez les informations affichées et validez avec l'option `Finish partitionning and write changes to disk`.

![récapitulatif installation Debian](images/E77Apuzy0h.png)

Si vous êtes sûr de vos réglages, positionnez vous sur l'option `Yes` et validez.

![confirmation finale](images/hZ5GA9aVD4.png)

Patientez pendant que Debian s'installe. Lordqu'on vous demande de scanner votre média d'installation, sélectionnez `No`.

![scanner le média d'installation](images/CSFJjD3Kyf.png)

Sélectionnez le plus proche mirroir d'archives.

![sélection du mirroir d'archives le plus proche](images/0Z4ZLcFxsL.png)

Sélectionnez le mirroir par défaut `deb.debian.org`.

![sélection du mirroir d'archive](images/L7esl9JRa4.png)

Saisissez le proxy si vous en avez un. Dans le cas contraire laissez le champ vide.

![sélection du proxy](images/EDS5TotyrT.png)

Choisissez si vous souhaitez envoyer des données anonymes aux développeurs.

![données envoyées au développeurs](images/HM4U7npXzf.png)

Sélectionnez les logiciels à installer. Cochez `standard system utilities`. Laissez le reste décoché.

![logiciels à installer](images/87BYu7qe7W.png)

Choisissez d'installer le `boot loader GRUB`.

![GRUB option](images/XRKUY3Bb4H.png)

Sélectionnez manuellement le disque où installer GRUB.

![sélection du disque pour GRUB](images/xtqQDQhJkn.png)

Si tout s'est bien passé jusque là, vous pouvez choisir de démarrer le système.

![installation complète](images/Af4WbUxpAi.png)

**Remarque :** Il existe de nombreuses étapes qui peuvent poser problème. Ce document ne peut lister tous les cas de figure alors je vous invite à chercher en ligne en cas de problème lors de cette installation.

#### Configuration de Debian

##### Notions de base

Sur Linux, la plupart des actions se font en ligne de commande. Certains outils ont une gestion automatisée via une interface graphique mais la plupart ne possèdent que des options en ligne de commande.

Une commande commence par le nom du programme/de la commande suivi de ses options. Il faut valider chaque commande  avec la touche `ENTRÉE`.

Chaque commande possède un manuel (généralement accessible en ligne) pour connaître les options qu'elle propose mais généralement, les débutants préfèrent chercher sur Internet car le manuel est souvent difficile d'accès.

##### L'éditeur de texte Nano

La commande `nano` suivie d'un chemin de fichier demande d'ouvrir ce fichier dans un éditeur de texte appelé *Nano*.

Les commandes de cet éditeur apparaissent au bas de l'écran.

**Attention !** Dans Nano, les commandes s'exécutent directement sans validation par la touche `ENTRÉE`.

- Pour quitter, appuyez sur `CTRL+X`.
- Pour sauvegarder le fichier édité, appuyez sur `CTRL+O`. Si le fichier existe déjà, son nom apparait en bas de la fenêtre pour vérification. Si c'est un nouveau fichier, vous devez saisir son nom. Validez si vous souhaitez vraiment sauvegarder vos modifications. Pour annuler la sauvegarde, appuyez sur `CTRL+O`.

##### Mise à jour du système 

En premier lieu, assurez-vous avant tout que le système est bien à jour. Pour cela, on commence par préciser qu'on veut saisir des commandes en mode super utilisateur (`su`), l'équivalent du mode Administrateur.

Saisissez la commande suivante et validez :

```
su -
```

**Remarque :** Pensez bien à séparer la commande et le tiret par un espace. L'espace sert de séparateur.

On utilise ensuite la commande `apt-get` qui permet d'installer, et de gérer la mise à jour de fonctionnalités sur le système. Ici on utilise l'opérateur `&&` pour appeler plusieurs commandes à la suite.

- L'option `update` met à jour les fonctionnalités déjà présentes.
- L'option `upgrade` met à niveau (installe la dernière version) les fonctionnalités déjà présentes.
- L'option `dist-upgrade` met à jour le système (la distribution Linux que vous avez installée).


Saisissez la commande suivante et validez :

```
apt-get update && apt-get upgrade && apt-get dist-upgrade
```

##### Synchronisation de l’horloge système

On s’assure que l’horloge système sera synchronisée grâce à `ntp`

```
apt-get install ntp ntpdate
```

Saisissez `Y` pour confirmer l'installation.

##### La commande sudo

`sudo` est une commande qui permet aux utilisateurs d’exécuter des commandes administrateur de manière temporaire. Il faut d'abord l'installer.

Pour l’installer il convient tout d’abord de s’authentifier en tant que `root` (administrateur principal) sur la machine (si ce n'est pas déjà fait).

```
su -
```

Pour quitter le compte super utilisateur, saisissez la commande `exit` :

```
exit
```

On utilise ensuite la commande `apt-get` pour installer (option `install`) la commande sudo.

```
apt-get install sudo
```

La commande `sudo` n'est accessible qu'aux membres du groupe qui lui sont associés ainsi qu'au compte `root`. Il faut donc ajouter l’utilisateur créé lors de l’installation au groupe sudo pour qu'il puisse utiliser lui aussi cette commande.

```
usermod -aG sudo NOM_UTILISATEUR
```

#### Installer un clone d'image Linux

Cliquez sur le bouton `Importer`.

![](images/4xF7iwdYH1.png)

![](images/kTEOieE6Zd.png)

![](images/Wuqa2vBv6g.png)

### Rendre fonctionnel la machine virtuelle jusqu'à la fin du TP

A démontrer lors de la soutenance.

### Permettre l'accès au réseau internet sur la machine virtuelle

Testez que la machine peut bien communiquer avec d'autres.

```
ping 1.1.1.1
```

![](images/zux5l8Nyhy.png)

Appuyez sur `CTRL+C` pour stopper le processus de ping.

## Partie 2 : Environnement

### Configuration de l'environnement Linux

#### Démarrer Debian

Lancez VirtualBox, sélectionnez la machine virtuelle de votre choix et cliquez sur le bouton `Démarrer`.

#### Eteindre la machine virtuelle

```
shutdown now
```

#### Voir les utilisateurs existants

```
nano /etc/passwd
```

![/etc/passwd](images/XbtVKIGFFl.png)

#### Créer un utilisateur

Lors de l'installation de Debian, vous avez créé un premier utilisateur. Si vous avez besoin d'en créer d'autres, utilisez la commande `useradd`.

```
useradd nom_utilisateur
```

Vous devez également définir un mot de passe avec la commande `password`.

```
passwd nom_utilisateur
```

Saisissez et confirmer le nouveau mot de passe pour cet utilisateur.

#### Supprimer un utilisateur

Utilisez la commande `userdel`.

```
userdel nom_utilisateur
```

#### Voir le nom de la machine

Le nom de la machine est stocké dans le fichier `/etc/hostname`. Pour le consulter, saisissez la commande :

```
nano /etc/hostname
```

Vous pouvez également utiliser la commande `hostname` sans paramètre pour afficher directement le nom actuel de la machine.

```
hostname
```

#### Modifier le nom de la machine

Vous pouvez modifier temporairement (jusqu'au prochain redémarrage) le nom de machine via la commande `hostname` suivie du nouveau nom.

```
hostname nouveau_nom
```

**Remarque :** Cette technique ne modifie pas le fichier `/etc/hostname`.

Pour modifier de manière permanente le nom de machine, le plus simple reste encore d'éditer le fichier `/etc/hostname`.

```
nano /etc/hostname
```

#### Définir une adresse IP fixe sur un réseau

**Attention !** L'adresse IP fixe est différente pour chaque réseau où la machine hôte est connectée.

##### Préparatif

Si vous n'avez pas de connection sur votre machine virtuelle, vous devez vérifier que VirtualBox utilise le bon périphérique.

Dans la barre des taches, cliquez sur les connexions. Notez le nom de la connexion actuelle.

![connexions Windows](images/C7WO8NXm39.png)

Ouvrez le panneau de configuration à la section `Panneau de configuration\Réseau et Internet\Connexions réseau`. Notez le nom du périphérique utilisé.

![Connexions réseau Windows](images/r4nqyUN3kN.png)

Dans VirtualBox, cliquez sur le bouton `Configuration`.

A la section `Réseau`, sélectionnez le périphérique.

![VirtualBox périphérique réseau](images/j65osGIIq3.png)

##### Trouver l'adresse IP du routeur

Sur la machine hôte Windows (pas la machine virtuelle), saisir la commande :

```
ipconfig
```

![demo ipconfig](images/gfdhjughjf.png)

La ligne `Adresse IPv4` indique l'adresse de la machine hôte. **N'utilisez pas cette IP pour la machine virtuelle !**

La ligne `Passerelle par défaut` indique l'adresse du routeur.

##### Changer l'adresse IP

Connectez-vous au réseau.

Avant de définir l'adresse IP, vous devez trouver l'identifiant du périphérique réseau à utiliser. Sur la machine virtuelle, utilisez la commande `ifconfig` (ou `ip a` si la commande précédente est indisponible) et notez l'identifiant du périphérique réseau.

```
ifconfig
```

ou

```
ip a
```

![affichage commande ifconfig](images/uOLA7pJiFE.png)

Editez ensuite le fichier `interfaces` situé dans le dossier `/etc/network/`.

```
nano /etc/network/interfaces
```

Modifiez le fichier comme ceci et sauvegardez :

```
# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug identifiant_peripherique
iface identifiant_peripherique inet static
	address adresse_à_donner_à_la_machine
	netmask 255.255.255.0
	gateway adresse_du_routeur
	dns-nameservers adresse_du_routeur
```

Choisissez une `adresse_à_donner_à_la_machine` pour qu'elle soit unique sur votre réseau. On change généralement le dernier nombre de l'adresse IP.

Supprimez la ligne d'IPv6 si elle est présente.

![fichier interfaces](images/RDLBsUO40z.png)

Relancez les périphériques réseaux avec la commande suivante :

```
ifup identifiant_peripherique
```

Si un message affiche que le périphérique est déjà configuré, utiliser d'abord la commande `ifdown` avant `ifup`.

```
ifdown identifiant_peripherique
ifup identifiant_peripherique
```

Vérifiez que votre IP est bien modifiée.

```
ip a
```

Testez que la machine peut bien communiquer avec d'autres.

```
ping 1.1.1.1
```

Appuyez sur `CTRL+C` pour stopper le processus de ping.

Si ce n'est pas le cas, ouvrez le fichier `/etc/resolv.conf`.

```
nano /etc/resolv.conf
```

Modifiez le fichier avec l'adresse du routeur et sauvegardez.

```
domain nom_domaine
search nom_domaine
nameserver adresse_du_routeur
```

### Installer, configurer et utiliser des outils reconnus pour permettre d’héberger des solutions web en toute fiabilité

#### Installation d'Apache

Saisissez la commande suivante :

```
apt-get install apache2
```

Saisissez `Y` pour valider l'installation d'Apache.

Vous devez installer des modules supplémentaires non installés par défaut.

```
a2enmod rewrite ssl actions include
```

Vous devez ensuite redémarrer Apache.

```
systemctl restart apache2
```

#### Vérifier qu'Apache est en démarrage automatique

Pour savoir si un service est lancé au démarrage, redémarrez la machine virtuelle puis saisissez la commande suivante :

```
service --status-all
```

- Un service avec `+` indique qu'il est démarré.
- Un service avec `-` indique qu'il est arrêté.

![services](images/U0Hm8fkkGI.png)

Le service `apache2` doit être démarré.

#### Vérifier qu'Apache fonctionne correctement

Testez qu'Apache fonctionne bien en ouvrant un navigateur sur votre système principal (pas la machine virtuelle) et en saisissant l'adresse IP de votre machine.

![Serveur web Apache](images/43FPFAHahM.png)

La racine des fichiers web se trouvent à l'emplacement `/var/www/html`.

```
cd /var/www/html
ls
```

#### Configurer un virtual host pour Apache

Un virtual host est un fichier de configuration qui associe un chemin de fichiers à un port réseau. Cela permet d'accéder à différents chemin sur la même adresse en changeant simplement de port.

Créer un dossier `/var/www/html/nom_domaine/public` pour stocker le site. Le dossier `public` permet d'indiquer quels fichiers sont accessibles.

```
mkdir -p /var/www/html/nom_domaine/public
```

**Remarque :** L'option `-p` crée un dossier ainsi que les dossiers parents si ceux ci n'existent pas.

Si on veut que l'utilisateur normal puisse accéder à ce dossier, nous devons lui attribuer les droits.

```
chown -R nom_utilisateur:nom_utilisateur /var/www/html/domaine.com/public
```

**Remarque :** L'option `-R` permet d'attribuer les droits récursivement dans tous les sous-dossiers.

Editez ensuite le fichier de configuration `/etc/apache2/sites-available/nom_domaine.conf`.

```
nano /etc/apache2/sites-available/nom_domaine.conf
```

Saisissez les informations sur ce modèle :

```
<VirtualHost *:80>
    ServerAdmin admin@nom_domaine
    ServerName nom_domaine
    ServerAlias www.nom_domaine
    DocumentRoot /var/www/html/nom_domaine/public
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
    <Directory /var/www/html/nom_domaine/public>
        Options Indexes FollowSymLinks
        AllowOverride All
    </Directory>
</VirtualHost>
```

**Attention !** Pensez bien à sauvegarder votre fichier !

![fichier vhost Apache](images/6jTDdJy3nL.png)

**Remarque :** Sur l'image précédente, il y a une faute sur `FollowSymLinks` ce qui a provoqué une erreur. Soyez très vigilant sur ce que vous saisissez.

Il est possible de créer plusieurs vhost dans un même fichier de configuration mais il est généralement plus simple de créer un fichier de configuration séparé pour chaque vhost.

On doit ensuite activer ce fichier de configuration.

```
a2ensite nom_domaine.conf
```

Et on doit à nouveau redémarrer Apache.

```
systemctl restart apache2
```

#### PHP

Installez l'interpréteur `php`.

```
apt-get install php
```

Saisissez `Y` pour valider l'installation.

![Version de PHP](images/0K7LDMJQpv.png)

Installez la bibliothèque d'interface entre PHP et Apache.

```
apt-get install libapache2-mod-php
```

![Place de libapache2-mod-php](images/kdj7X.png)

Positionnez vous dans le dossier `/var/www/html`.

```
cd /var/www/html
```

Créer un fichier `info.php`.

```
nano info.php
```

Saisissez le texte suivant dans ce fichier et sauvegardez.

```
<?php
phpinfo();
?>
```

Testez si PHP est correctement configuré en ouvrant votre navigateur sur votre système principal (pas la machine virtuelle) et en saisissant l'adresse IP de la machine virtuelle suivie de `/info.php`.

![test PHP](images/7WncbCgpBa.png)

#### Installation de la base de données MariaDB


Installez la base de données MariaDB.

```
apt-get install mariadb-server
```

Saisissez `Y` pour valider.

#### Configuration de Maria DB

Initialisez MariaDB.

```
mysql_secure_installation
```

- Saisissez le mot de passe de l'administrateur de la base de données.
- Saisissez `n` pour la question `Switch to unix_socket authentication`.
- Saisissez `n` pour la question `Change the root password`.
- Saisissez `n` pour la question `Remove anonymous users`.
- Saisissez `n` pour la question `Disallow root login remotely`.
- Saisissez `Y` pour la question `Remove test database and access to it`.
- Saisissez `Y` pour la question `Reload privilege tables now`.

Redémarrez le service associé.

```
systemctl restart mariadb
```

Démarrez MariaDB.

```
mysql
```

![Exécution de MariaDB](images/3De0stha8s.png)

Pour quitter MariaDB, saisissez la commande `exit`.

```
exit
```

#### PHPMyAdmin

Installez le package `php-mysql` pour que PHP puisse accéder à MariaDB.

```
apt-get install php-mysql
```

Saisissez `Y` pour valider l'installation.

```
apt-get install phpmyadmin
```

Cochez l'option `Apache` et validez.

![option phpmyadmin Apache](images/V3yRlFOLd4.png)

Choisissez d'utiliser `dbconfig-common`.

![dbconfig-common](images/VHR0sqHHm1.png)

Saisissez deux fois le mot de passe administrateur.

Testez si phpmyadmin fonctionne. Ouvrez un navigateur sur la machine hôte. Saisissez l'adresse IP de la machine virtuelle suivie de `/phpmyadmin`.

```
XXX.XXX.XXX.XXX/phpmyadmin
```

![test de phpmyadmin](images/cwcCgLhNIS.png)

#### Créer un alias dans le fichier hosts de la machine hôte

Vous pouvez accéder au site du serveur web (Apache) depuis une machine cliente si vous utilisez l'adresse IP de la machine virtuelle dans le navigateur.

```
XXX.XXX.XXX.XXX
```

Il vaut mieux toutefois configurer le fichier `hosts` de la machine cliente pour accéder au site en utilisant un nom de domaine.

Vous devez éditer le fichier `hosts` de votre machine cliente pour associer l'adresse IP de la machine virtuelle où est hébergée le serveur web et le nom de domaine.

Sur Windows, ce fichier `hosts` se situe à l'emplacement `C:\Windows\System32\drivers\etc\`.

Sur Linux, ce fichier `hosts` se situe à l'emplacement `/etc/`.

Ouvrez le fichier `hosts` avec un éditeur de texte. Ajoutez une ligne avec l'adresse IP de la machine virtuelle suivie du nom de domaine.

```
XXX.XXX.XXX.XXX nom_domaine
```

![fichier hosts édité](images/aWsLRLB5OM.png)

## Partie 3 : Premier site

### Se rendre dans le répertoire "www"

Allez dans le dossier `/var/www`.

```
cd /var/www
```

### Créer un nouveau projet dans le répertoire "www" avec des fichiers PHP

Créez un dossier `monsite`.

```
mkdir monsite
```

Entrez dans ce dossier.

```
cd monsite
```

Créez un fichier `index.php` dans ce nouveau dossier.

```
nano index.php
```

Saisissez le code suivant et sauvegardez.

```
<?php
phpinfo();
?>
```

### Les projets sont accessibles depuis un navigateur (machine hôte ou autre machine du réseau)

Pour accéder à ce fichier depuis un navigateur, vous devez créer un nouveau vhost.

Editez le fichier de configuration `/etc/apache2/sites-available/monsite.conf`.

```
cd /etc/apache2/sites-available
nano monsite.conf
```

Saisissez les informations sur ce modèle :

```
<VirtualHost *:80>
    ServerAdmin admin@monsite
    ServerName monsite.com
    ServerAlias www.monsite.com
    DocumentRoot /var/www/monsite
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
    <Directory /var/www/monsite>
        Options Indexes FollowSymLinks
        AllowOverride All
    </Directory>
</VirtualHost>
```

On doit ensuite activer ce fichier de configuration.

```
a2ensite monsite.conf
```

Et on doit à nouveau redémarrer Apache.

```
systemctl restart apache2
```

Vous devez éditer le fichier `hosts` de votre machine cliente pour associer l'adresse IP de la machine virtuelle où est hébergée le serveur web et le nom de domaine `monsite.com`.

Sur Windows, ce fichier `hosts` se situe à l'emplacement `C:\Windows\System32\drivers\etc\`.

Sur Linux, ce fichier `hosts` se situe à l'emplacement `/etc/`.

Ouvrez le fichier `hosts` avec un éditeur de texte. Ajoutez une ligne avec l'adresse IP de la machine virtuelle suivie du nom de domaine.

```
XXX.XXX.XXX.XXX monsite.com
```

Ouvrez le navigateur et saisissez l'adresse `monsite.com`.

![monsite.com](images/EyAguSyHvP.png)

## Partie 4 : Accès au site et sécurisation

### Installer SSH

Par défaut, le client SSH est déjà installé sur les systèmes.

```
ssh -V
```

Vous devez installer le serveur SSH.

```
apt-get install openssh-server
```

Saisissez `Y` pour valider l'installation.

**Remarque :** Il est également possible de le faire lors de l'installation de Debian.

Vérifiez que le serveur fonctionne.

```
systemctl status sshd
```

![Status du serveur SSH](images/ME76AYDzMT.png)

Assurez vous que le serveur démarre au lancement du système.

```
systemctl enable ssh
```

**Remarque :** Vous pouvez désactiver le serveur via la commande `systemctl stop sshd`.

### Identifier le répertoire contenant les fichiers utilisés par le client SSH

- Sur la machine hôte, le fichier de configuration SSH `known_hosts` est situé à l'emplacement `C:\Users\nom_utilisateur\.ssh\`.
- Sur la machine virtuelle, les fichiers de configuration SSH sont situés à l'emplacement `/etc/ssh`.

### Configurer le serveur SSH

- Le fichier `ssh_config` définit les règles SSH pour les clients.
- Le fichier `sshd_config` définit les règles SSH pour votre serveur SSH. Il définit le port SSH accessible ou refuser l'accès de certains utilisateurs à votre serveur.

Ouvrez le fichier `sshd_config`.

```
nano sshd_config
```

Par défaut, le serveur SSH s'exécute sur le port `22`. Modifiez le port utilisé.

Recherchez la ligne suivante :

```
#Port 22
```

Décommentez la ligne (en supprimant `#`) et modifiez le numéro de port du serveur SSH. Choisissez un port qui n'est pas déjà utilisé par un de vos services.

```
Port 2222
```

**Attention !** Souvenez-vous de ce numéro de port quand vous voudrez accéder au serveur SSH.

Par défaut, on peut s'identifier en tant qu'administrateur (*root*) sur le serveur SSH. Désactivez cette possibilité.

Recherchez la ligne suivante :

```
#PermitRootLogin
```

Et modifiez la comme ceci :

```
PermitRootLogin no
```

A la fin du fichier, ajoutez la ligne suivante :

```
Allowgroups sshusers
```

Sauvegardez.

SSH propose deux façons de se connecter. Par mot de passe ou par clé d'authentification. Le projet exige d'utiliser la seconde façon.

Créez un couple de clé publique et privée.

```
ssh-keygen
```

Vous devez préciser l'emplacement où générer ces clés. Le message suivant apparait.

```
Generating public/private rsa key pair.
Enter file in which to save the key (/home/username/.ssh/id_rsa):
```

Appuyez sur `ENTREE` pour choisir l'emplacement par défaut (`/home/username/.ssh` ou `/root/username/.ssh` si la commande a été passée en tant que *root*).

Appuyez sur `ENTREE` deux fois pour laisser une phrase de sécurité vide.

Positionnez vous dans le dossier où ont été générées les clés.

![clés SSH](images/0YdlCejQ7T.png)

- Le fichier `id_rsa` est la clé privée. Elle se place au niveau du serveur. Ne la communiquez à personne.
- Le fichier `id_rsa.pub` est la clé publique. C'est cette clé qu'il faut transmettre aux clients qui souhaitent se connecter au serveur SSH.



Après toutes ces configurations du serveur SSH, redémarrez le service.

```
systemctl restart sshd
```

### Se connecter en SSH depuis une autre machine du réseau (et de manière sécurisée et renforcée)

S’assurer qu’il est bien possible de se connecter en SSH depuis une autre machine (par exemple avec la machine hôte).

Il devra être possible d’ajouter à tout moment un nouvel utilisateur « distant » pouvant se 
connecter en SSH avec son compte.

### Configurer le pare-feu en adéquation avec la stratégie

Installez le firewall `ufw` qui est très simple d'utilisation.

```
apt-get install ufw
```

Activez `uwf`.

```
ufw enable
```

Par défaut, tous les ports sont fermés. Ouvrez les ports que vous souhaitez utiliser. Pour le projet, vous aurez besoin du port `80` pour le serveur web Apache et le port SSH (par défaut `22` mais que vous devriez avoir modifié).

```
ufw allow 80
ufw allow port_ssh
```

### Créer deux utilisateurs virtuels (Dev1 et Dev2)

➢ Créer 2 utilisateurs virtuels « Dev1 » et « Dev2 » qui pourront interagir avec le serveur web
• Chaque utilisateur (développeur) aura un répertoire virtuel

### Chaque utilisateur virtuel accède au dossier `monsite` et ne peut pas en sortir

• Chaque utilisateur accédera par défaut au répertoire « monsite » et ne pourra pas en 
sortir (jail)
• Les utilisateurs ne peuvent pas modifier les fichiers « systèmes »

### Se connecter en SFTP depuis une autre machine

Client SFTP 

Téléchargez le client SSH [WinSCP](https://winscp.net/eng/index.php).

Tester depuis la machine hôte de se connecter avec un client SFTP (exemple : WinSCP)

➢ Se connecter en SFTP avec chaque utilisateur (tester)

### Modifier le fichier par défaut du site (monsite)

Modifier le fichier par défaut du site

###  Rendre les changement visibles depuis un navigateur

Tester en affichant la page web « modifiée » dans le navigateur.

## Partie 5 : La base de données

Connectez-vous à la base de données.

```
mysql -u root -p
```

### Une base de données est existante et opérationnelle

Créez une base de données, vous pourrez la nommer `cesibdd`.

```
CREATE DATABASE cesibdd;
```

### Créez un utilisateur

Créez un nouvel utilisateur `dibdd`. Le mot de passe sera `dibdd`.

```
CREATE USER 'dibdd@localhost' IDENTIFIED BY 'dibdd';
```

### Attribuez les privilèges maximum à cet utilisateur

Attribuez-lui les privilèges maximum sur cette nouvelle base de données.

```
GRANT ALL PRIVILEGES ON *.* TO 'dibdd'@'localhost';
FLUSH PRIVILEGES;
```

### Connectez-vous à la base de données avec l'utilisateur `dibdd`

```
mysql -u dibdd@localhost -p
```

## Partie 6 : Installation d'un nouveau site

➢ Vous devrez le placer directement dans le répertoire www d’Apache
➢ Veillez à bien conserver votre premier dossier monsite (du dossier www)
▪ Installer le CMS
➢ En cas de difficulté, pensez à lire le fichier README.txt à la racine du projet (CMS)
▪ Créer un nouveau vhost pointant sur le dossier
▪ Se connecter en administrateur sur le CMS nouvellement installé
2. Modification CMS 
▪ Modifier la page d’accueil de votre site
▪ Ajouter un ou deux contenus
▪ Personnaliser le site comme bon vous semble

### Un CMS est déployé sur le serveur web il est fonctionnel, accessible et l'on peut modifier le contenu



### Un vhost est configuré et permet d'accéder au site autrement que par l'IP



### Installation du CMS Wordpress

Positionnez-vous dans le dossier `/var/www/`.

```
cd /var/www
```

Téléchargez l'archive de Worpress :

```
wget https://wordpress.org/latest.tar.gz
```

Décompressez l'archive :

```
tar -xzvf latest.tar.gz
```

Le dossier `wordpress` conrrespond à la racine du site Wordpress.

Supprimez l'archive devenue inutile.

```
rm latest.tar.gz
```

### Configuration de Wordpress

Ouvrez le navigateur et accédez au domaine associé au chemin vers Wordpress sur le serveur web :

[A REDIGER]

### Configuration d'un vhost pour Wordpress

Editez le fichier de configuration `/etc/apache2/sites-available/wordpress.conf`.

```
nano /etc/apache2/sites-available/wordpress.conf
```

Saisissez les informations sur ce modèle :

```
<VirtualHost *:80>
    ServerAdmin admin@nom_domaine
    ServerName nom_domaine
    ServerAlias www.nom_domaine
    DocumentRoot /var/www/html/nom_domaine/public
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
    <Directory /var/www/html/nom_domaine/public>
        Options Indexes FollowSymLinks
        AllowOverride All
    </Directory>
</VirtualHost>
```

On doit ensuite activer ce fichier de configuration.

```
a2ensite wordpress.conf
```

Et on doit à nouveau redémarrer Apache.

```
systemctl restart apache2
```

### Configuration du fichier hosts

La machine qui souhaite consulter le site sur le serveur web doit configurer son fichier `hosts` pour associer le nom de domaine avec l'adresse IP du serveur.

```
XXX.XXX.XXX.XXX nom_domaine
```

- Sur Windows, le fichier `hosts` se trouve à l'emplacement `C:/windows/system32/drivers/etc`.
- Sur Linux, le fichier `hosts` se trouve à l'emplacement `/etc/`.

Sur le serveur, le fichier `hosts` doit également être configuré car le serveur web peut proposer plusieurs noms de domaines. Il faut associer le nom de domaine avec l'adresse IP `127.0.0.1`.

```
127.0.0.1 localhost nom_domaine
```

Testez que vous pouvez accéder au site Wordpress via l'adresse `nom_domaine/` dans le navigateur de la machine hôte.

![Wordpress demo](images/IQOGOv6uay.png)

Cliquez sur le bouton `Let's go!`.

![Wordpress configuration](images/n2uYRFF0v1.png)

[PROBLEME - A REVOIR]

## Partie 7 : Serveur Pré-prod - Prod

[FAIT MAIS A REDIGER]
Pour réaliser cette partie, il est conseillé d’être à deux (avec votre binôme). L’un jouera le 
rôle du serveur pré-prod, l’autre le rôle du serveur de production. Vous pourrez changer 
les rôles afin d’aborder chacun les objectifs

Idéalement, vous serez dans la même configuration. Si ce n’est pas le cas, n’hésitez pas à dupliquer 
(cloner) le serveur3
le plus abouti / fonctionnel des deux.
✓ Serveur A = Serveur de pré-production
✓ Serveur B = Serveur de production
Test 
▪ Dans un premier temps essayez de pinger le serveur A depuis le serveur B avec leur nom (et 
non pas leur adresse IP)
▪ Essayez ensuite d’afficher le site depuis un navigateur du même réseau
▪ Connectez-vous en SSH sur le serveur de développement (Serveur A)
A ce stade, vous devriez avoir quelques contenus sur votre serveur A (Cf. chapitre précédent –
Modification CMS). Si ce n’est pas le cas, merci de vous y reporter avant de passer à la suite.
Préparation à la migration du site 

Ici, nous allons migrer (en prod) le site du serveur A vers le serveur B.

1. Faire une extraction de la base de données (dump SQL) dans son état actuel
2. Connectez-vous en SFTP sur le serveur
3. Récupérer la base de données « dumpée »
4. Récupérer si nécessaire l’archive des dossiers « personnalisé » de votre CMS
➢ Ici, nous parlons des dossiers et fichiers qui ont pu être ajouté ou qui aurait pu évoluer
depuis l’installation du CMS
➢ Lire la documentation du CMS ou suivre un article / tuto expliquant comment migrer / 
déployer le site
Serveur de production 
Entre le serveur A et le serveur B
1. Récupérer les sources (dossiers du site CMS sauvegardés) du serveur A et les copier sur le 
serveur B
2. Importer la BDD « dumpées » du serveur A vers le serveur B
3. Modifier les éventuels fichiers de configuration natifs du CMS de manière à ce que le site soit 
opérationnel sur le serveur B.
➢ Lire la documentation officielle du CMS
➢ Suivre un article / tuto au sujet de la migration / déploiement du CMS concerné
4. Depuis la machine hôte ou depuis le serveur A, tester le bon fonctionnement et affichage du 
site nouvellement déployé sur le serveur B.

### Il y a 2 serveurs qui communiquent (ping et ssh)



### La Migration est fonctionnelle (Dump SQL / Import SQL / Structures)



### Les 2 sites sont identiques (contenus)



## Partie 8 : Automatisation

[FAIT MAIS A REDIGER]
Créer un script qui permet : 
• Lorsque l’on va créer un nouvel utilisateur son site web portant son nom sera créé.
• Le répertoire par défaut de l’utilisateur sera /home/<UTILISATEUR>/public_html
• Créer un répertoire logs par utilisateur
• Stocker l’horodatage de la création du compte dans un fichier
Création d’un nouvel utilisateur 
▪ Créer un nouvel utilisateur « cesien » (ce sera votre profil pour le développement)
▪ Assurez-vous que l’on puisse accéder à la page web4 de l’utilisateur via son nom
Il vous sera demandé de faire une démonstration lors de la correction.



### Un script d'automatisation sera créé lors de l'ajout d'un user.



### Dossier logs existant +  Stockage de l'horodatage (création de compte) dans un fichier



### Accès à un dossier "public_html" dans le repertoire de l'utilisateur



### Le script fonctionne lors de l'ajout d'un nouveau user



### Une tâche quotidienne sauvegarde automatiquement la BDD

Utilisez `cron` pour exécuter une tâche quotidienne. Vérifiez que son status est bien actif.

```
systemctl status cron
```

Placez-vous dans le dossier `/etc/cron.daily`.

```
cd /etc/cron.daily
```

Créez un script pour sauvegarder la base de données.

```
nano save_database.sh
```

Saisissez le code suivant :

```
#!/bin/bash

# date du jour
backupdate=$(date +%Y-%m-%d)

#répertoire de backup
dirbackup=/backup/backup-$backupdate

# création du répertoire de backup
/bin/mkdir $dirbackup

# sauvegarde de la base de données mysql dans un fichier gzip
/usr/bin/mysqldump --user=xxxx --password=xxxx --all-databases | /usr/bin/gzip > $dirbackup/mysqldump-$backupdate.sql.gz
```

Modifiez les droits du fichier script.

```
chmod 700 save_database.sh
```

## Partie 9 : Sécurisation du site et disponibilité

### HTTPS activé et fonctionel (au moins le self-signed)

Utilisez le protocole cryptographique SSL (Secure Socket Layer) pour activer la certification HTTPS et la sécurisation du site.

Le protocol SSL créé un canal sécurisé entre deux machines.

Installez le module SSL d'Apache pour qu'il puisse traiter les requêtes HTTPS et les certificats.

```
a2enmod ssl
```

Redémarrez le service Apache.

```
systemctl restart apache2
```

Créez les certificats SSL.

```
sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/apache-selfsigned.key -out /etc/ssl/certs/apache-selfsigned.crt
```

Saisissez vos informations.

![Exemple d'informations pour le certificat SSL](images/LCCZk0rtp0.png)

Modifiez votre fichier vhost. Positionnez-vous dans le dossier `/etc/apache2/sites-enabled`.

```
cd /etc/apache2/sites-enabled
```

Editez le fichier de configuration `000-default.conf`.

```
nano 000-default.conf
```

Créez un nouveau virtual host en port `443` pour chacun des sites (copiez-les et modifiez juste le port) et ajoutez les lignes suivantes :

```
SSLEngine on
SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
```

```
# MONSITE
<VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

# MONSITE SSL
<VirtualHost *:443>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
</VirtualHost>

# WORDPRESS
<VirtualHost *:80>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

# WORDPRESS SSL
<VirtualHost *:443>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
</VirtualHost>
```

Sauvegardez puis redémarrez le service Apache.

```
service apache2 restart
```

Autorisez l'accès au port `443` dans le pare-feu.

```
ufw allow 443
```

Assurez-vous que le pare-feu est activé.

```
ufw enable
```

### URL Rewriting mis en place sur le site et fonctionnel

Modifiez votre fichier vhost. Positionnez-vous dans le dossier `/etc/apache2/sites-enabled`.

```
cd /etc/apache2/sites-enabled
```

Editez le fichier de configuration `000-default.conf`.

```
nano 000-default.conf
```

Ajoutez les lignes suivantes aux vhosts en port `80` :

```
RewriteEngine On
RewriteCond %{HTTPS}  !=on
RewriteRule ^/?(.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

```
# MONSITE
<VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        RewriteEngine On
        RewriteCond %{HTTPS}  !=on
        RewriteRule ^/?(.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>

# MONSITE SSL
<VirtualHost *:443>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
</VirtualHost>

# WORDPRESS
<VirtualHost *:80>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        RewriteEngine On
        RewriteCond %{HTTPS}  !=on
        RewriteRule ^/?(.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>

# WORDPRESS SSL
<VirtualHost *:443>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key
</VirtualHost>
```

Si ce n'est pas déjà fait, activez le service `rewrite`.

```
a2enmod rewrite
```

Sauvegardez puis redémarrez le service Apache.

```
service apache2 restart
```

### Créer des redirections vers des pages d'erreurs 401, 403, 404, 500

Créez une page d'erreur (une page HTML statique) pour chacune des erreurs `401`, `403`, `404`, `500`. Tranférez les si besoin de votre machine hôte vers la machine virtuelle via le logiciel SFTP.

Créez un dossier `errors` dans le dossier de Wordpress.

```
cd /var/www/wordpress
mkdir errors
```

Placez les pages dans le dossier `errors`. Puis ouvrez le fichier de configuration vhost.

Positionnez-vous dans le dossier `/etc/apache2/sites-enabled`.

```
cd /etc/apache2/sites-enabled
```

Editez le fichier de configuration `000-default.conf`.

```
nano 000-default.conf
```

Ajoutez les lignes suivantes aux vhosts en port `443` :

```
ErrorDocument 404 /errors/404.html
ErrorDocument 401 /errors/401.html
ErrorDocument 403 /errors/403.html
ErrorDocument 500 /errors/500.html
```

```
# MONSITE
<VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        RewriteEngine On
        RewriteCond %{HTTPS}  !=on
        RewriteRule ^/?(.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>

# MONSITE SSL
<VirtualHost *:443>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/monsite

        <Directory /var/www/monsite>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key

        ErrorDocument 404 /errors/404.html
        ErrorDocument 401 /errors/401.html
        ErrorDocument 403 /errors/403.html
        ErrorDocument 500 /errors/500.html
</VirtualHost>

# WORDPRESS
<VirtualHost *:80>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        RewriteEngine On
        RewriteCond %{HTTPS}  !=on
        RewriteRule ^/?(.*) https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
</VirtualHost>

# WORDPRESS SSL
<VirtualHost *:443>
        ServerName preprod.domaine.com
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/wordpress

        <Directory /var/www/wordpress>
          Options Indexes FollowSymLinks
          AllowOverride All
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

        SSLEngine on
        SSLCertificateFile /etc/ssl/certs/apache-selfsigned.crt
        SSLCertificateKeyFile /etc/ssl/private/apache-selfsigned.key

        ErrorDocument 404 /errors/404.html
        ErrorDocument 401 /errors/401.html
        ErrorDocument 403 /errors/403.html
        ErrorDocument 500 /errors/500.html
</VirtualHost>
```

Sauvegardez puis redémarrez le service Apache.

```
service apache2 restart
```

## Partie 10 : Bonus

### Le cache est mis en place

[A FAIRE]
Cache 
Mettre en place un système de cache sur l’un de vos projets (exemple : memcache)

### Le Loadbalancing est mis en place

[A FAIRE]
Load Balancing 
La répartition de charge (= load balancing en anglais, littéralement équilibrage de charge) est une 
technique utilisée en informatique pour distribuer un travail entre plusieurs serveurs.
Les avantages sont nombreux 
▪ Augmentation de la qualité des services
▪ Amélioration des temps de réponse des services
▪ Capacité à pallier la défaillance d'une ou de plusieurs machines
▪ Possibilité d'ajouter des serveurs sans interruption de service
Mise en place 
Mettre en place un système de Load Balancing sur l’instance de votre serveur. L’outil haproxy
permet d’atteindre ces objectifs.
Cf. Annexe 2 – Schéma simplifié d’un système de Load Balancing
Vous pouvez vous informer ici : https://linuxfr.org/forums/linux-general/posts/tuto-howto-ubuntu debian-load-balancing-redirection-vers-plusieurs-vhost-avec-haproxy
