# Redirection

## Redirection https://www.domaine.fr vers https://domaine.fr

Bonjour,

Dans ce tutoriel, vous allez tous simplement apprendre à rediriger votre domaine de type https://www.domaine.fr vers https://domaine.fr (environ 2 minutes).

Prérequis.

* Serveur Web
* Prise en compte .htaccess
* Fichier .htaccess à la racine de votre site internet

On débute maintenant la mise en place de la redirection

Ouvrer le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^https://www.domaine.fr [NC]
RewriteRule ^(.*)$ https://domaine.fr/$1 [L,R=301][/CODE]
```
Vous pouvez des à présent profiter de votre site.


## Redirection https://domaine.fr vers https://www.domaine.fr

Bonjour,

Dans ce tutoriel, vous allez tous simplement apprendre à rediriger votre domaine de type https://domaine.fr vers https://www.domaine.fr (environ 2 minutes).

Prérequis.

* Serveur Web
* Prise en compte .htaccess
* Fichier .htaccess à la racine de votre site internet

On débute maintenant la mise en place de la redirection
Ouvrer le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^https://domaine.fr [NC]
RewriteRule ^(.*)$ https://www.domaine.fr/$1 [L,R=301]
```

Vous pouvez des à présent profiter de votre site.

## Redirection http://domaine.fr vers http://www.domaine.fr

Bonjour,

Dans ce tutoriel, vous allez tous simplement apprendre à rediriger votre domaine de type http://domaine.fr vers http://www.domaine.fr (environ 2 minutes).

Prérequis.

* Serveur Web
* Prise en compte .htaccess
* Fichier .htaccess à la racine de votre site internet

On débute maintenant la mise en place de la redirection
Ouvrer le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^domaine.fr [NC]
RewriteRule ^(.*)$ http://www.domaine.fr/$1 [L,R=301]
```

Vous pouvez des à présent profiter de votre site.

## Redirection http://www.domaine.fr vers http://domaine.fr

Bonjour,

Dans ce tutoriel, vous allez tous simplement apprendre à rediriger votre domaine de type http://www.domaine.fr vers http://domaine.fr (environ 2 minutes).

Prérequis.

* Serveur Web
* Prise en compte .htaccess
* Fichier .htaccess à la racine de votre site internet

On débute maintenant la mise en place de la redirection
Ouvrer le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^www.domaine.fr [NC]
RewriteRule ^(.*)$ http://domaine.fr/$1 [L,R=301]
```

Vous pouvez des à présent profiter de votre site.

## Redirection HTTP vers HTTPS

Bonjour,

Dans ce tutoriel, vous allez tous simplement apprendre à rediriger votre domaine http vers https (environ 2 minutes).

Prérequis.

* Serveur Web
* Certificats SSL de disponible
* Prise en compte .htaccess

Fichier .htaccess à la racine de votre site internet

On débute maintenant la mise en place de la redirection

Redirection de tous vos domaines (redirection simple du trafic)
Ouvrer le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI} [R,L]
```

Redirection dans le cas si vous possédez plusieurs domaines sur votre (hébergement, VPS, Dédié)

Ouvrir le fichier .htaccess
Ajouter le code ci-dessous

```php
RewriteEngine On
RewriteCond %{HTTP_HOST} ^MonDomaine\.fr [NC]
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI}
```

Vous pouvez des à présent profiter de votre site en HTTPS.