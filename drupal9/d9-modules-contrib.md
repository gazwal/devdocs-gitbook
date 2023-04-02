# Modules Contrib

[https://www.drupal.org/project/file\_delete](https://www.drupal.org/project/file\_delete)TODO : Ressources "Choix de modules indispensables" :

* [The 9 Drupal Modules I use on Literally Every Build in 2020](https://mikemadison.net/blog/2020/7/12/the-9-drupal-modules-i-use-on-literally-every-build-in-2020)
* [Mon Top 30 des modules Drupal 8](https://makina-corpus.com/blog/metier/2019/top-drupal-modules)
*

{% hint style="info" %}
Modules Indispensables = <mark style="background-color:green;">\*\*\*\*\*</mark> 5 étoiles
{% endhint %}

## **Administration / Configuration / BO admin :**

* [Admin Toolbar](https://www.drupal.org/project/admin\_toolbar) <mark style="background-color:green;">\*\*\*\*\*</mark> ok D10\
  `composer require drupal/admin_toolbar`
* [Module Filter](https://www.drupal.org/project/module\_filter) <mark style="background-color:green;">\*\*\*\*\*</mark> ok D10\
  `composer require drupal/module_filter`
* [Backup and Migrate](https://www.drupal.org/project/backup\_migrate) <mark style="background-color:green;">\*\*\*\*\*</mark> ok D10\
  `composer require drupal/backup_migrate`



* [Pathauto](https://www.drupal.org/project/pathauto) <mark style="background-color:green;">\*\*\*\*\*</mark> ok D10\
  `composer require drupal/pathauto`
* [Transliterate filenames for uploads](https://www.drupal.org/project/transliterate\_filenames) <mark style="background-color:green;">\*\*\*\*\*</mark>\
  \=>Transliteration for all uploading files (includes fields and CKEditor inline uploads)

## Utilitaires

* [Override Node Options](https://www.drupal.org/project/override\_node\_options) ok D10







## Gestion des fichiers (file entity) :

Voir la série d'articles : [https://www.webwash.net/how-to-replace-files-in-drupal/](https://www.webwash.net/how-to-replace-files-in-drupal/)

* [File Replace (D8+)](https://www.drupal.org/project/file\_replace) ok D10 => intéressant, à tester =>BOF au final, pas sur que cela fonctionne\
  _The file replace module is a small utility providing site administrators with the possibility to replace files, keeping the file uri intact. This is useful in cases where a file is linked or used directly but needs to be updated occasionally._\
  _=>voir le tuto :_ [_https://www.webwash.net/how-to-replace-files-in-drupal/_](https://www.webwash.net/how-to-replace-files-in-drupal/)__

**Suppression des fichiers inutiles / n'appartenant plus à un contenu :**

De base, en admin, on a la view : /admin/content/files

* [File Delete](https://www.drupal.org/project/file\_delete) : modifie la view /admin/content/files pour y rajouter un bouton de suppression. Fonctionne pour supprimer ponctuellement un fichier. Suppression immédiate en utilisant Drush.
* &#x20;[Fancy File Delete](https://www.drupal.org/project/fancy\_file\_delete) : plus complet que ci-dessus, mais pareil, résoud pas le souci des fichiers non utilisés dans les nodes , alors qu'ils apparraissent
* __[_Unmanaged / Unused Files | Manage | Delete_](https://www.drupal.org/project/unmanaged\_files) _=> BAD !!! PLANTAGE !!! au 05/01/2022, sous drupal 9.5.1 et php 8.1.13_
*













## Edition de node / Back Office client

* [Views Bulk Operations (VBO)](https://www.drupal.org/project/views\_bulk\_operations) + [Views Bulk Edit](https://www.drupal.org/project/views\_bulk\_edit) <mark style="background-color:green;">\*\*\*\*\*</mark>\
  `composer require drupal/views_bulk_operations`\
  `composer require drupal/views_bulk_edit`
* [Meta position](https://www.drupal.org/project/meta\_position) <mark style="background-color:green;">\*\*\*\*\*</mark>\
  `composer require drupal/meta_position`\
  ``=> quasi indispensable pour l'édition des nodes, en attente d'un thème de BO qui soit impeccable
* [Field Group](https://www.drupal.org/project/field\_group) \*\*\*\
  `composer require drupal/field_group`
*



## DEV / Utilitaires / Spécials / Twig

* [Devel](https://www.drupal.org/project/devel)\
  `composer require drupal/devel`
* [VarDumper](https://www.drupal.org/project/vardumper)\
  `composer require drupal/vardumper`
* [Twig VarDumper](https://www.drupal.org/project/twig\_vardumper)\
  [https://git.drupalcode.org/project/twig\_vardumper/-/blob/3.0.x/README.md](https://git.drupalcode.org/project/twig\_vardumper/-/blob/3.0.x/README.md)\
  `composer require drupal/twig_vardumper`
* [**Twig Tweak**](https://www.drupal.org/project/twig\_tweak) **/** [**Cheat sheet**](https://git.drupalcode.org/project/twig\_tweak/-/blob/3.x/docs/cheat-sheet.md) **/** [**Docs**](https://www.drupal.org/docs/contributed-modules/twig-tweak/twig-tweak-and-views) **/** [**Cheat sheet 2.X**](https://www.drupal.org/docs/contributed-modules/twig-tweak-2x/cheat-sheet)****\
  ****composer require drupal/twig\_tweak\
  Docs :\
  Functions and filters to get you started with Twig Tweak in Drupal 8 (with examples)
* [Twig Field Value](https://www.drupal.org/project/twig\_field\_value)\
  `composer require drupal/twig_field_value`
* [Quick Node Clone](https://www.drupal.org/project/quick\_node\_clone)\
  `composer require drupal/quick_node_clone`
* xxx

## SEO

* [Simple XML sitemap](https://www.drupal.org/project/simple\_sitemap)\
  `composer require drupal/simple_sitemap`
*

## Taxonomy

* [Client-side Hierarchical Select\
  ](https://www.drupal.org/project/cshs)`composer require drupal/cshs`
*
