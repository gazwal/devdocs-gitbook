# Install & Composer

## Install via [rupal-composer/drupal-project](https://github.com/drupal-composer/drupal-project)

### **What does the template do?**

When installing the given `composer.json` some tasks are taken care of:

* Drupal will be installed in the `web`-directory.
* Autoloader is implemented to use the generated composer autoloader in `vendor/autoload.php`, instead of the one provided by Drupal \(`web/vendor/autoload.php`\).
* Modules \(packages of type `drupal-module`\) will be placed in `web/modules/contrib/`
* Theme \(packages of type `drupal-theme`\) will be placed in `web/themes/contrib/`
* Profiles \(packages of type `drupal-profile`\) will be placed in `web/profiles/contrib/`
* Creates default writable versions of `settings.php` and `services.yml`.
* Creates `web/sites/default/files`-directory.
* Latest version of drush is installed locally for use at `vendor/bin/drush`.
* Latest version of DrupalConsole is installed locally for use at `vendor/bin/drupal`.
* Creates environment variables based on your .env file. See [.env.example](https://github.com/drupal-composer/drupal-project/blob/8.x/.env.example).

```text
// utilisation du kickstarter drupal-composer/drupal-project => github
composer create-project drupal-composer/drupal-project:8.x-dev some-dir --stability dev --no-interaction

// pour notre projet, on se place dans le répertoire WWW et on lance la commande :
composer create-project drupal-composer/drupal-project:8.x-dev drupal8_dev1 --stability dev --no-interaction
```

### Mise à jour Drupal Core

Lire la doc !! [https://github.com/drupal-composer/drupal-project](https://github.com/drupal-composer/drupal-project)

### Activer l'environnement de DEV = mode Debug

=&gt; [https://www.drupalfacile.org/question/comment-mettre-drupal-8-mode-developpement-avec-settingslocalphp](https://www.drupalfacile.org/question/comment-mettre-drupal-8-mode-developpement-avec-settingslocalphp)  
=&gt; [https://github.com/zivtech/bear\_skin/blob/8.x-2.x/docs/dev\_mode.md](https://github.com/zivtech/bear_skin/blob/8.x-2.x/docs/dev_mode.md)

{% hint style="info" %}
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

### Installation, Mise à jour, Suppression

```text
// Lister tous les packages outdated
composer outdated --direct

// Lister que les packages Drupal outdated
composer outdated "drupal/*"

// Installation de modules/themes
composer require drupal/admin_toolbar
composer require drupal/views_bulk_operations:^3.0
composer require drupal/admin_toolbar:^2.0

// Mise à jour de modules/themes
composer update drupal/admin_toolbar --with-dependencies
composer update drupal/facets drupal/search_api drupal/views_accordion --with-dependencies
drush updatedb
drush cr

// Suppression de modules/themes
(après l'avoir désinstallé dans drupal !!)
composer remove drupal/admin_toolbar

```

## Documentations

2018/11  
Part 1: [Understanding Composer](https://www.morpht.com/blog/drupal-and-composer-part-1-understanding-composer)  
Part 2: [Managing a Drupal 8 site with Composer](https://www.morpht.com/blog/drupal-and-composer-part-2-managing-drupal-8-site-composer)  
Part 3: [Converting Management of an Existing Drupal 8 Site to Composer](https://www.morpht.com/blog/drupal-and-composer-part-3-converting-management-existing-drupal-8-site-composer)  
Part 4: [Composer for Drupal Developers](https://www.morpht.com/blog/drupal-and-composer-part-4-composer-drupal-developers)  


