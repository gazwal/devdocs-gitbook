# Install & Composer

## Install via pantheon.io

Drupal 9 updates Drupal’s underlying dependencies like [Symfony 4.4](https://symfony.com/releases/4.4) and [Twig 2](https://twig.symfony.com/doc/2.x/index.html), removes several deprecated API functions in favor of better options, and allows everyone running Drupal 8.8+ an easy upgrade path to Drupal 9 and beyond.

doc : [https://pantheon.io/docs/drupal-9](https://pantheon.io/docs/drupal-9)

{% hint style="success" %}
On the Pantheon Platform, Drupal 9 sites use [**Integrated Composer**](https://pantheon.io/docs/integrated-composer), letting you deploy your site on Pantheon with one-click updates for both upstream commits and Composer dependencies, while still receiving upstream updates.
{% endhint %}

Le template est sur Github aussi :

{% embed url="https://github.com/pantheon-upstreams/drupal-project" %}

## Install normal via composer

Lire la doc officielle : [3.5. Using Composer to Download and Update Files](https://www.drupal.org/docs/user_guide/en/install-composer.html)

```text
// Installation de drupal dans le dossier "drupal9-composer"
$ composer create-project drupal/recommended-project drupal9-composer
```

Autres ressources :   
[Installer Drupal 9 avec Composer](https://www.itss.paris/blog/installer-drupal-9-avec-composer)  
[Mettre à jour son projet Composer et envisager sereinement la montée de version à Drupal 9](https://www.kaliop.com/fr/mettre-a-jour-son-projet-composer-et-envisager-sereinement-la-montee-de-version-a-drupal-9/)  
  


