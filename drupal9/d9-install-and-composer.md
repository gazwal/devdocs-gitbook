# Install & Composer

## Install via pantheon.io

Drupal 9 updates Drupal’s underlying dependencies like [Symfony 4.4](https://symfony.com/releases/4.4) and [Twig 2](https://twig.symfony.com/doc/2.x/index.html), removes several deprecated API functions in favor of better options, and allows everyone running Drupal 8.8+ an easy upgrade path to Drupal 9 and beyond.

doc : [https://pantheon.io/docs/drupal-9](https://pantheon.io/docs/drupal-9)

{% hint style="success" %}
On the Pantheon Platform, Drupal 9 sites use [**Integrated Composer**](https://pantheon.io/docs/integrated-composer), letting you deploy your site on Pantheon with one-click updates for both upstream commits and Composer dependencies, while still receiving upstream updates.
{% endhint %}

Le template est sur Github aussi :

{% embed url="https://github.com/pantheon-upstreams/drupal-project" %}

{% hint style="danger" %}
Après avec cloné le site via panthéon, il faut mettre en place un **settings.local.php**, sinon plantage du site panthéon car les infos de BDD sont commitées. Voir ci-dessous.
{% endhint %}

## MISE à jour via pantheon.io

1 - on applique la MAJ via l'interface d'administration  
2 - on fait un $ git pull sur notre servion locale pour télécharger les changements  
3 - En général, c'est le composer.lock qui est mis à jour  
4 - on lance un $ composer install sur notre version locale  
5 - lancer un /update.php sur le site locale

{% hint style="danger" %}
QUAND ya une mise à jour côté pantheon : en local on fait :  
$ git pull =&gt; ça met à jour uniquement le composer.json donc :  
**ne pas oublié de faire un de faire un $ composer install + update.php via l'administration**

$ git pull origin master  
$ composer install  
$ drush updb  
$ drush cr
{% endhint %}

## Install normal via composer

Lire la doc officielle : [3.5. Using Composer to Download and Update Files](https://www.drupal.org/docs/user_guide/en/install-composer.html)

[Using Composer to Install Drupal and Manage Dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-install-drupal-and-manage-dependencies#download-core-option-a)

```text
// Exemple : Installation de drupal dans le dossier "drupal9-composer"
$ composer create-project drupal/recommended-project drupal9-composer
```

Autres ressources :   
[Installer Drupal 9 avec Composer](https://www.itss.paris/blog/installer-drupal-9-avec-composer)  
[Mettre à jour son projet Composer et envisager sereinement la montée de version à Drupal 9](https://www.kaliop.com/fr/mettre-a-jour-son-projet-composer-et-envisager-sereinement-la-montee-de-version-a-drupal-9/)

## !!! DEV local + mode Debug !!!

{% hint style="danger" %}
**settings.php =&gt; settings.local.php =&gt; development.services.yml  
ou  
settings.php =&gt; settings.local.php =&gt; local.development.services.yml**
{% endhint %}

**1\) copier le fichier /sites/example.settings.local.php** et le mettre dans  
/sites/default/example.settings.local.php  
le renommer en **settings.local.php**

**2\) Éditer le fichier settings.php** et :  
- activer \(= dé-commenter\) la prise en compte du fichier settings.local.php \(ligne 770 ...\)

```text
if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
  include $app_root . '/' . $site_path . '/settings.local.php';
}
```

**3\) development.services.yml =&gt; twig debug**  
Le fichier settings.local.php appelle le fichier /sites/development.services.yml  
ou un autre nom =&gt; ex : local.development.services.yml

```text
/**
 * Enable local development services.
 */
// $settings['container_yamls'][] = DRUPAL_ROOT . '/sites/development.services.yml';
$settings['container_yamls'][] = DRUPAL_ROOT . '/sites/local.development.services.yml';
```

On édite donc le fichier development.services.yml et on rajoute les services de debug pour TWIG.  
\(on copie les infos se trouvant dans /sites/default/default.services.yml , lignes 39, pour les coller dans /sites/development.services.yml\)

```text
parameters:
  twig.config:
    debug: true
    auto_reload: true
    cache: false
```

Vider le cache après ttes ces modif ou avec drush :

```text
drush cr
```

{% hint style="info" %}
**important ! :**  
dans settings.local.php, il y a des mise en cache à désactiver :  
- Disable the render cache.  
- Disable caching for migrations.  
- Disable Internal Page Cache.  
- Disable Dynamic Page Cache.

**ligne non commentée = le cache est désactivé**  
lorsque que les caches sont désactivés, le site est très lent. A utilisé que lorsque qu'on taff sur du DEV de fichiers twig ou du debug !!
{% endhint %}

## Commandes Composer w/ Drupal

```text
// Installation de modules/themes
composer require drupal/admin_toolbar
composer require drupal/views_bulk_operations:^3.0
composer require drupal/admin_toolbar:^2.0
composer require drupal/backup_migrate:5.0.0-rc2

// Installer plusieurs modules d'un coup : on sépare avec des espaces
$ composer require drupal/adminimal_theme:^1.5 drupal/adminimal_admin_toolbar:^1.9

// Lister tous les packages outdated
composer outdated --direct

// Lister que les packages Drupal outdated
composer outdated "drupal/*"



// Mise à jour de modules/themes
composer update drupal/admin_toolbar --with-dependencies
composer update drupal/facets drupal/search_api drupal/views_accordion --with-dependencies
drush updatedb
drush cr

// Suppression de modules/themes
(après l'avoir désinstallé dans drupal !!)
composer remove drupal/admin_toolbar

```

Installation de versions spécifiques d'un module :

[https://drupal.stackexchange.com/questions/192164/how-can-i-force-composer-to-install-a-dev-branch-over-a-stable-release](https://drupal.stackexchange.com/questions/192164/how-can-i-force-composer-to-install-a-dev-branch-over-a-stable-release)  
[https://modulesunraveled.com/drupal-8-composer-and-configuration-management/installing-dev-version-modules](https://modulesunraveled.com/drupal-8-composer-and-configuration-management/installing-dev-version-modules)

## MAJ Drupal core w/ Composer

[Updating Drupal core via Composer](https://www.drupal.org/docs/updating-drupal/updating-drupal-core-via-composer) \*\*\*\*

voir aussi en fin de cet article les instructions détaillées : [Detailed update instructions](https://www.drupal.org/docs/updating-drupal/updating-drupal-core-via-composer#update-all-steps)

```text
// voir si on utilise le template core-recommended
composer show drupal/core-recommended
```

* If drupal/core-recommended is **installed**, this command returns information about the package.
* If drupal/core-recommended is **not installed,**  this command returns "Package drupal/core-recommended not found".

```text
// Check for available Drupal update
composer outdated "drupal/*"

// UPGRADE
// With the metapackage drupal/core-recommended
composer update drupal/core "drupal/core-*" --with-all-dependencies

// Run database update
drush updatedb

// Rebuild cache
drush cache:rebuild
```

{% hint style="danger" %}
Lors de l'upgrade en LOCAL, j'ai l'erreur :

`[RuntimeException]  
Could not delete /Users/robin/www/drupal9-composer/web/sites/default/default.services.yml`

Il faut "set file permissions to allow _user_ and _group_ to write to the file on your local machine:"  
Voir : [https://drupal.stackexchange.com/questions/290296/composer-require-fails-because-it-cant-delete-default-services-yml](https://drupal.stackexchange.com/questions/290296/composer-require-fails-because-it-cant-delete-default-services-yml)

```text
$ chmod ug+w web/sites/default
```
{% endhint %}

#### MAJ d'un site de prod <a id="s-update-the-production-environment-when-applicable"></a>

On

## MAJ Modules/Theme w/ Composer

```text
// Lister tous les packages outdated
composer outdated --direct

// Lister que les packages Drupal outdated
composer outdated "drupal/*"

// Installation de modules/themes
composer require drupal/admin_toolbar
composer require drupal/views_bulk_operations:^3.0
composer require drupal/admin_toolbar:^2.0

// Mise à jour de modules/themes spécifiques
composer update drupal/admin_toolbar --with-dependencies
composer update drupal/backup_migrate --with-dependencies
// plusieurs d'un coup
composer update drupal/facets drupal/search_api drupal/views_accordion --with-dependencies

// Mise à jour d'un module vers une autre version ############
// ex: backup_migrate 5.0.0-rc2 => 5.0.1 est dispo
// composer update drupal/backup_migrate --with-dependencies NE DONNE RIEN
// du coup on relance un $composer require
composer require drupal/backup_migrate
// là on a bien un "upgrade" vers 5.0.1 :
// Upgrading drupal/backup_migrate (5.0.0-rc2 => 5.0.1)


// ############ pas oublier pour finir :
drush updatedb
drush cr

// Suppression de modules/themes
(après l'avoir désinstallé dans drupal !!)
composer remove drupal/admin_toolbar

```

## Upgrage d8 -&gt; d9

[Upgrading from Drupal 8 to Drupal 9 \(or later\)](https://www.drupal.org/docs/upgrading-drupal/upgrading-from-drupal-8-to-drupal-9-or-later)

Site de type "tarball" :  
_Upgrading a tarball-based site from Drupal 8 to Drupal 9 with Drush requires an older version of Drush: Drush 8. See_ [_Update core via Drush_](https://www.drupal.org/docs/8/update/update-core-via-drush) _for instructions on how to do this._

  


## DDEV

A tester un jour :

[https://ddev.readthedocs.io/en/stable/users/cli-usage/\#drupal-9-quickstart](https://ddev.readthedocs.io/en/stable/users/cli-usage/#drupal-9-quickstart)

{% embed url="https://github.com/drud/ddev" %}

{% embed url="https://ddev.readthedocs.io/en/stable/users/cli-usage/\#drupal-9-quickstart" %}

**voir** [**docker-ddev**](../dev-tools/docker-ddev.md)\*\*\*\*

