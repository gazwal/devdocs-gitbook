---
description: A Dependency Manager for PHP
---

# Composer

### Installation

Composer est un "Dependency Manager for PHP" = un outil pour gérer les dépendances en PHP.  
Composer permet de gérer pour chaque projet, la liste des modules et bibliothèques nécessaires à son fonctionnement ainsi que leurs versions.  
Pour utiliser Composer, tout se passe dans le fichier **composer.json**

**Avant d'installer Composer**, on édite le .bash\_profile pour rajouter un alias pour PHP.  
**Afin que composer utilise le PHP de MAMP**  
=&gt; ici un exemple [https://gist.github.com/kkirsche/5710272](https://gist.github.com/kkirsche/5710272)

```text
// edition du fichier
$ sudo nano .bash_profile
// on rajoute la ligne suivante :
alias php="/Applications/MAMP/bin/php/php7.2.1/bin/php"
```

Ce qui donne au final \(au 2019.11.05\) :

```text
export PATH="/Applications/MAMP/Library/bin:/Applications/MAMP/bin/php/php7.2.1/bin:$PATH"
alias php="/Applications/MAMP/bin/php/php7.2.1/bin/php"
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
```

Attention, une fois quitté l'édition, on doit recharger notre config bash avec

```text
$ source .bash_profile
```

Ensuite, pour installer Composer, on suit la doc, on est dans /Users/robin \(= la racine mbprobin:~ robin$\)  
doc = [https://getcomposer.org/download/](https://getcomposer.org/download/)

```text
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');" 
php -r "if (hash_file('SHA384', 'composer-setup.php') === 'aa96f26c2b67226a324c27919f1eb05f21c248b987e6195cad9690d5c1ff713d53020a02ac8c217dbf90a7eacc9d141d') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;" 
php composer-setup.php
php -r "unlink('composer-setup.php');" 
```

Il faut ensuite effectuer ces 2 commandes  
voir [https://getcomposer.org/doc/00-intro.md\#globally](https://getcomposer.org/doc/00-intro.md#globally) \(pour installer Composer globalement Important !!\)

```text
$ mv composer.phar /usr/local/bin/composer
$ chmod +x /usr/local/bin/composer
```

Vérifier sa version de composer

```text
mbprobin:~ robin$ composer --version
Composer version 1.9.0 2019-08-02 20:55:32
```

### **Mettre à jour composer**

avec la commande $ composer self-update

```text
mbprobin:~ robin$ composer self-update
Updating to version 1.7.2 (stable channel).
   Downloading (100%)
Use composer self-update --rollback to return to version 1.4.1
mbprobin:~ robin$
---------
robin@mbprobin ~ % composer self-update
Updating to version 2.1.3 (stable channel).
   Downloading (100%)
Use composer self-update --rollback to return to version 1.9.0
```

**Commandes Composer :**

```text
composer.json: defines metadata about the project and dependencies for the project.
composer.lock: metadata file containing computed information about dependencies and expected install state.
composer install: downloads and installs dependencies, also builds the class autoloader. If a .lock file is available it will install based off of the metadata. Otherwise it will calculated and resolve the download information for dependencies.
composer update: updates defined dependencies and rebuilds the lock file.
composer require: adds a new dependency, updates the JSON and .lock file.
composer remove: removes a dependency, updates the JSON and .lock file.
```

```text
Le fonctionnement de Composer (en mode utilisateur) est assez simple, il requiert de connaître un peu sa terminologie :

composer.json: définit les metadonnées du projet et de ses dépendances.
composer.lock: fichier de métadonnées qui contient les informations calculées à propos des dépendances et de leur état (versions, urls, etc.).
composer install: télécharge et installe les dépendances, construit l'autoloader de classes PHP. Si un fichier .lock est présent, il installera les dépendances en fonction de celui-ci, sinon il calculera et résoudra les informations sur les versions et les urls pour les dépendances.
composer update: met à jour les dépendances et reconstruit le fichier .lock.
composer require: ajoute une nouvelle dépendance, mettant à jour les fichiers .json et .lock.
composer remove: retire une dépendance, mettant à jour les fichiers .json et .lock.

Toutes les commandes de Composer doivent être exécutées *dans le même répertoire que votre fichier composer.json*.
```

**Pleins de commandes :**

{% embed url="https://devhints.io/composer" %}



