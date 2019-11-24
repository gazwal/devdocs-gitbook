# API - Services

[**Services and Dependency Injection Container**](https://api.drupal.org/api/drupal/core!core.api.php/group/container/)  
Liste de tous les services : [https://api.drupal.org/api/drupal/services/](https://api.drupal.org/api/drupal/services/)

Ressources web \(FR\)  
[Drupal 8 : Conteneur de Services et Services](https://happyculture.coop/blog/drupal-8-conteneur-de-services-et-services) \(Happyculture\)  
[Drupal 8 à votre service !](https://www.flocondetoile.fr/blog/drupal-8-votre-service) \(Flocon ce Toile\)

> Les applications modernes s’appuyant sur la POO, beaucoup d’objets sont impliqués dans le cycle de vie d’une page. Afin de vous épargner la création, la réutilisation et la suppression de chacun de ces nombreux objets, Drupal 8 s’appuie sur un objet spécial de Symfony appelé **Service Container** qui vise à vous simplifier la manipulation de ces dits objets.  
>  Comme son nom l’indique, le **Conteneur de Services** gère des **Services**.

{% hint style="info" %}
Un service est un objet PHP, conçu dans le but d'atteindre un objectif spécifique, qui effectue une sorte de tâche globale.
{% endhint %}

#### \Drupal::service\('image.factory'\)

[https://api.drupal.org/api/drupal/core!core.services.yml/service/image.factory](https://api.drupal.org/api/drupal/core!core.services.yml/service/image.factory)  
test ici =&gt; /www/gazwal-d8/modules/custom/gazwal\_utils  
Voir aussi :  
[Image file objects are classed](https://www.drupal.org/node/2084547)  
[Drupal 8: rendering a image programmatically](https://vdmi.nl/blog/drupal-8-rendering-image-programmatically)  
[Flexible image style system](https://www.drupal.org/node/2050669)  


#### \Drupal::service\('path.current'\)

[https://api.drupal.org/api/drupal/core!core.services.yml/service/path.current](https://api.drupal.org/api/drupal/core!core.services.yml/service/path.current)

#### \Drupal::service\('path.alias\_manager'\)

[https://api.drupal.org/api/drupal/core!core.services.yml/service/path.alias\_manager](https://api.drupal.org/api/drupal/core!core.services.yml/service/path.alias_manager)



