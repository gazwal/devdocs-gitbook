# Theming

## [CSS coding standards](https://www.drupal.org/docs/develop/standards/css/css-coding-standards) / SMACSS

```text
cuddly-slider:
  version: 1.x
  css:
    layout:
      css/cuddly-slider-layout.css: {}
    theme:
      css/cuddly-slider-theme.css: {}
  js:
    js/cuddly-slider.js: {}
```

You may notice the 'layout' and 'theme' keys for css which is not present for js. This indicates the style type the css file belongs to.

You can set `CSS` weights with 5 different levels of styling:

* `base`: CSS reset/normalize plus HTML element styling. Key assigns a weight of `CSS_BASE = -200`
* `layout`: macro arrangement of a web page, including any grid systems. Key assigns a weight of `CSS_LAYOUT = -100`
* `component`: discrete, reusable UI elements. Key assigns a weight of `CSS_COMPONENT = 0`
* `state`: styles that deal with client-side changes to components. Key assigns a weight of `CSS_STATE = 100`
* `theme`: purely visual styling \(“look-and-feel”\) for a component. Key assigns a weight of `CSS_THEME = 200`

This is defined by the [SMACSS](https://smacss.com/) standard. So here if you specify theme it means that the CSS file contains theme related styling which is pure look and feel. [More info here](https://www.drupal.org/node/1887922). You **cannot** use other _keys_ as these will cause strict warnings.

{% hint style="info" %}
Drupal 8 follows a SMACSS-style categorization of its CSS rules:

1. Base — CSS reset/normalize plus HTML element styling.
2. Layout — macro arrangement of a web page, including any grid systems.
3. Component — discrete, reusable UI elements.
4. State — styles that deal with client-side changes to components.
5. Theme — purely visual styling \(“look-and-feel”\) for a component.
{% endhint %}

## Javascript / Libraries

[Adding stylesheets \(CSS\) and JavaScript \(JS\) to a Drupal 8 theme](https://www.drupal.org/docs/8/theming/adding-stylesheets-css-and-javascript-js-to-a-drupal-8-theme#all-pages) \(THEME\) \*\*\*  
[Drupal ES6 Javascript Behaviors](http://slidedeck.io/danielbeeke/drupal-javascript-behaviors) \*\*\*  
[La gestion des librairies avec Drupal 8](https://www.flocondetoile.fr/blog/la-gestion-des-librairies-avec-drupal-8)  
[Drupal 8 : Gestion des librairies, Point sur le monde JS](https://happyculture.coop/blog/drupal-8-gestion-des-librairies-point-sur-le-monde-js) \*\*\* \(drupalSettings\)

Attacher une librairie :

```php
// dans un template twig
{{ attach_library('fluffiness/cuddly-slider') }}
<div>Some fluffy markup {{ message }}</div>

// ou via un preprocess
function fluffiness_preprocess_maintenance_page(&$variables) {
  $variables['#attached']['library'][] = 'fluffiness/cuddly-slider';
}
```

Overrider des librairies

```yaml
libraries-override:
  # Remplacer une librairie entière.
  core/drupal.collapse: mytheme/collapse
  
  # Remplacer une ressouce par une autre.
  subtheme/library:
    css:
      theme:
        css/layout.css: css/my-layout.css
  
  # Supprimer une ressource.
  drupal/dialog:
    css:
      theme:
        dialog.theme.css: false
  
  # Supprimer une librairie entière.
  core/modernizr: false
```

**libraries-extend** permet aux thèmes d'altérer les ressources fournies par une librairie en leur déclarant des dépendances supplémentaires.

```text
  # Extend drupal.user: add assets from flocon/user library.
libraries-extend:
  core/drupal.user: 
    - flocon/user
```

## Ressources web \(EN\)

[Drupal 8 Theming Guide \(Acquia COG\)](https://github.com/acquia-pso/cog/tree/8.x-1.x/starterkit/_theming-guide) \*\*\*

## Ressources web \(FR\)

[La gestion des librairies avec Drupal 8](https://www.flocondetoile.fr/blog/la-gestion-des-librairies-avec-drupal-8)



