# Linux

## Installation serveur Mysql (MariaDB) Debian 9

### Attention fait pour debian 9

Dans ce tutoriel, vous allez tous simplement apprendre à créer un serveur Mysql (environ 5 - 10 minutes).

Tout d'abord, vous devez savoir pourquoi le serveur sera un serveur Mysql MariaDB.
Tous simplement, car la dernière version en date de Debian (V9) Mysqlserver à était remplacer par MariaDB
Noter qu'aucun changement réel n'est présent vous l’utiliserais de la même façon vous aurait juste une stabilité plus présente comparé à Mysqlserver.

Débutons par la mise à jour de votre serveur Dédié - VPS.

* apt-get update (Mise à jour des sources)
* apt-get upgrade (Upgrade des package déjà présent)

On débute maintenant l'installation de MariaDB

* apt install mariadb-server-10.1 -y

Création du mot de passe Root (par défaut, aucun n'est présent)

* Exécuter la commande : mysql -u root -p mysql (Il vous demandera un mot de passe laisser vide)

Une fois connecter sur le serveur Mysql vous allez faire les commande suivante

* UPDATE mysql.user SET plugin = NULL WHERE user = 'root' AND plugin = 'unix_socket';
* FLUSH PRIVILEGES;
* SET PASSWORD FOR root@'localhost'=PASSWORD('VOTE NOUVEAU MOT DE PASSE');
* exit

### Supplémentaire (panel d'administration)

L'installateur vous demandera un mot de passe à définir celui-ci vous servira à administrer votre serveur

   PHPMyAdmin (Panel d'administration pour votre serveur Mysql)

* apt-get install phpmyadmin -y

Vous pouvez des à présent débuté l'utilisation de votre premier serveur Mysql !
Vous allez trouver votre panel d'administration à l'adresse : votreip/phpmyadmin

Information : utilisateur : root Mot de passe : définis lors de la création du mot de passe.

## Activation prise en compte Htaccess

Dans ce tutoriel, vous allez tous simplement apprendre à créer un serveur Mysql (environ 2 à 3 minutes).

Prérequis.

* Serveur Web
* Linux: Debian 8 ou 9

On débute maintenant l'installation

Rendez-vous dans le fichier : /etc/apache2/sites-available/000-default.conf

Vous allez trouvez à la fin du fichier ceci 

* < /VirtualHost >

Juste au-dessus vous y ajouterais ceci

```php
<Directory /var/www/html/>
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    Order allow,deny
    allow from all
</Directory>
```

Pour finir

* Exécuter la commande :  a2enmod rewrite
* Terminer par la commande : /etc/init.d/apache2 restart


Vous pouvez des à présent utiliser vos htaccess !

## Installation serveur Mysql Debian 8

### Attention fait pour debian 8

Dans ce tutoriel, vous allez tous simplement apprendre à créer un serveur Mysql (environ 5 minutes).

Débutons par la mise à jour de votre serveur Dédié - VPS.

* apt-get update (Mise à jour des sources)
* apt-get upgrade (Upgrade des package déjà présent)

On débute maintenant l'installation de MySQL

* apt-get install mysql-server mysql-client libmysqlclient15-dev mysql-common -y

 
### Supplémentaire (panel d'administration)

L'installateur vous demandera un mot de passe à définir celui-ci vous servira à administrer votre serveur

   PHPMyAdmin (Panel d'administration pour votre serveur Mysql)

* apt-get install phpmyadmin -y

Vous pouvez des à présent débuté l'utilisation de votre premier serveur Mysql !
Vous allez trouver votre panel d'administration à l'adresse : votreip/phpmyadmin

* Information : utilisateur : root Mot de passe : définis lors de l'installation.

## Installation serveur Web (Lamp) (PHP 5) Debian 8

### Attention fait pour debian 8

Dans ce tutoriel, vous allez tous simplement apprendre à créer un serveur Lamp (environ 2 - 3).

Débutons par la mise à jour de votre serveur Dédié - VPS.

* apt-get update (Mise à jour des sources)
* apt-get upgrade (Upgrade des package déjà présent)

On débute maintenant l'installation de Apache 2

* apt-get install apache2 apache2-doc apache2-mpm-prefork apache2-utils libexpat1 ssl-cert -y
     
	 PHP 5 (Contiens toutes les extensions principales)

* apt-get install libapache2-mod-php5 php5 php5-common php5-curl php5-dev php5-gd php5-idn php-pear php5-imagick php5-imap php5-json php5-mcrypt php5-memcache php5-mhash php5-ming php5-mysql php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl -y

Si toute l'installation s'est déroulé correctement vous allez arriver sur une page par défaut html.


Vous pouvez des à présent débuté la mise en ligne de votre premier site internet !

* Le dossier se trouve à la racine de /var/www/html/
* Le fichiers index.html présent, vous pouvez le supprimer celui-ci et la page par défaut qui vous montre le bon fonctionnement après l'installation.

## Installation serveur Web (Lamp) (PHP 7.0) Debian 9

### Attention fait pour debian 9

Dans ce tutoriel, vous allez tous simplement apprendre à créer un serveur Lamp (environ 2 - 3).

Débutons par la mise à jour de votre serveur Dédié - VPS.

apt-get update (Mise à jour des sources)
apt-get upgrade (Upgrade des package déjà présent)

On débute maintenant l'installation de Apache 2

* apt-get install apache2 apache2-mod-php7.0 libapache2-mod-php7.0 -y

     PHP 7.0 (Contiens toutes les extensions principales)

* apt-get install php7.0 php7.0-mysql php7.0-curl php7.0-gd php7.0-intl php7.0-cli php7.0-cgi php7.0-imagick php7.0-imap php7.0-mcrypt php7.0-memcache php7.0-pspell php7.0-recode php7.0-snmp php7.0-sqlite php7.0-tidy php7.0-xmlrpc php7.0-xsl php7.0-imagick imagemagick libruby php7.0-memcached memcached -y

Si toute l'installation s'est déroulé correctement vous allez arriver sur cette page:

Vous pouvez des à présent débuté la mise en ligne de votre premier site internet !

* Le dossier se trouve à la racine de /var/www/html/
* Le fichiers index.html présent, vous pouvez le supprimer celui-ci et la page par défaut qui vous montre le bon fonctionnement après l'installation.