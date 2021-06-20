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

{% hint style="info" %}
QUAND ya une mise à jour côté pantheon : en local on fait :  
$ git pull =&gt; ça met à jour uniquement le composer.json donc :  
**ne pas oublié de faire un $ composer install + update.php via l'administration**
{% endhint %}

## Install normal via composer

Lire la doc officielle : [3.5. Using Composer to Download and Update Files](https://www.drupal.org/docs/user_guide/en/install-composer.html)

[Using Composer to Install Drupal and Manage Dependencies](https://www.drupal.org/docs/develop/using-composer/using-composer-to-install-drupal-and-manage-dependencies#download-core-option-a)

```text
// Installation de drupal dans le dossier "drupal9-composer"
$ composer create-project drupal/recommended-project drupal9-composer
```

Autres ressources :   
[Installer Drupal 9 avec Composer](https://www.itss.paris/blog/installer-drupal-9-avec-composer)  
[Mettre à jour son projet Composer et envisager sereinement la montée de version à Drupal 9](https://www.kaliop.com/fr/mettre-a-jour-son-projet-composer-et-envisager-sereinement-la-montee-de-version-a-drupal-9/)

## !!! DEV local + mode Debug !!!

{% hint style="danger" %}
**settings.php =&gt; settings.local.php =&gt; development.services.yml**
{% endhint %}

**1\) copier le fichier /sites/example.settings.local.php** et le mettre dans /sites/default/example.settings.local.php  
le renommer en **settings.local.php**

**2\) Éditer le fichier settings.php** et :  
- activer \(dé-commenter\) la prise en compte du fichier settings.local.php \(ligne 770 ...\)

```text
if (file_exists($app_root . '/' . $site_path . '/settings.local.php')) {
  include $app_root . '/' . $site_path . '/settings.local.php';
}
```

**3\) development.services.yml =&gt; twig debug**  
Le fichier settings.local.php appelle le fichier /sites/development.services.yml  
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
lorsque que les caches sont désactivés, le site est très lent. A utilisé que lorsque qu'on taff sur de dev de fichiers twig ou du debug !!
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

  


