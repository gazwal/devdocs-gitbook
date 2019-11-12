# Install & Composer

### Install via [rupal-composer](https://github.com/drupal-composer)/[**drupal-project**](https://github.com/drupal-composer/drupal-project)

### What does the template do?

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

## Documentations

2018/11  
Part 1: [Understanding Composer](https://www.morpht.com/blog/drupal-and-composer-part-1-understanding-composer)  
Part 2: [Managing a Drupal 8 site with Composer](https://www.morpht.com/blog/drupal-and-composer-part-2-managing-drupal-8-site-composer)  
Part 3: [Converting Management of an Existing Drupal 8 Site to Composer](https://www.morpht.com/blog/drupal-and-composer-part-3-converting-management-existing-drupal-8-site-composer)  
Part 4: [Composer for Drupal Developers](https://www.morpht.com/blog/drupal-and-composer-part-4-composer-drupal-developers)  


