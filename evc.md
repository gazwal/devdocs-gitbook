---
description: JUIN 2020 - eVisa Center
---

# EVC

Site de DEV ici : [http://gazwal.alwaysdata.net/EVC/evc-pages](http://gazwal.alwaysdata.net/EVC/evc-pages/)

Page Pays : [http://gazwal.alwaysdata.net/EVC/evc-pages/pays.php](http://gazwal.alwaysdata.net/EVC/evc-pages/pays.php)

{% hint style="danger" %}
ATTENTION : merci de supprimer la plupart des commentaires HTML dans le code pour la mise en production ;-)\
`<!-- Bla Bla Bla Commentaire HTML Bla Bla Bla -->`
{% endhint %}

## Librairies, CSS, JS :

Voir les fichiers :\
.**./evc-include/inc-head.php**\
**../evc-include/inc-footer-scripts.php**\
\
NB : toutes les pages ont le même "template" et chargent les mêmes librairies, CSS et JS

**EVC CSS :**\
(compilée via SASS : ../sass/evc-styles.scss)\
../evc-css/evc-styles.css => version normale non minifiée\
../evc-css/evc-styles.min.css => version minifiée de production

**EVC JS :**\
../evc-js/evc.js

## jQuery

Utilisation de jQuery 3.5.1 comme recommandé dans la doc Bootstrap 4.5.x :\
[https://getbootstrap.com/docs/4.5/getting-started/introduction/#js](https://getbootstrap.com/docs/4.5/getting-started/introduction/#js)\
**JS :**\
../evc-lib/js/jquery-3.5.1.min.js => version minifiée de production

## Bootstrap

&#x20;Utilisation de la dernière version de Bootstrap => 4.5.0 (Juillet 2020)\
&#x20;[https://getbootstrap.com/docs/4.5/getting-started/introduction/](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

**CSS :**\
****(compilée via SASS : ../sass/bootstrap.scss)\
****../evc-css/bootstrap.css => version normale non minifiée\
../evc-css/bootstrap.min.css => version minifiée de production

**JS :** utilisation de **bootstrap.bundle.min.js** qui inclus Popper.js\
(requis pour utiliser bootstrap-select)\
../evc-lib/js/bootstrap.bundle.min.js => version minifiée de production

## Bootstrap-Select

Permet la re-écriture des SELECT via javascript; et rajoute de nombreuses fonctionnalités, à explorer :\
[https://developer.snapappointments.com/bootstrap-select/](https://developer.snapappointments.com/bootstrap-select/)

**demo /exemples :**\
&#x20;[https://developer.snapappointments.com/bootstrap-select/examples/](https://developer.snapappointments.com/bootstrap-select/examples/)\
&#x20;[https://thdoan.github.io/bootstrap-select/examples.html](https://thdoan.github.io/bootstrap-select/examples.html)

**Permet aussi de mettre des drapeaux SVG dans les SELECT** => mon code utilise l'attribut data-content="" pour mettre les images, voir ici aussi :\
&#x20;[https://developer.snapappointments.com/bootstrap-select/examples/#custom-content](https://developer.snapappointments.com/bootstrap-select/examples/#custom-content)\
&#x20;[https://github.com/snapappointments/bootstrap-select-temp/issues/18](https://github.com/snapappointments/bootstrap-select-temp/issues/18)

**CSS :**\
****(compilée via SASS : ../sass/bootstrap-select.scss)\
****../evc-css/bootstrap-select.css => version normale non minifiée\
../evc-css/bootstrap-select.min.css => version minifiée de production

**JS :**\
../evc-lib/js/bootstrap-select.min.js => version minifiée de production

## Slick carousel

{% embed url="https://kenwheeler.github.io/slick/" %}

Utilisé pour le carousel / slider :\
\- en page d'accueil => section.home-01\
\- dans le sidebar => ../evc-include/inc-aside-page-pays.php

**CSS :**\
****(compilée via SASS : ../sass/slick.scss + ../sass/slick-theme.scss)\
\
****../evc-css/slick.css => version normale non minifiée\
../evc-css/slick.min.css => version minifiée de production

../evc-css/slick-theme.css => version normale non minifiée\
../evc-css/slick-theme.min.css => version minifiée de production

**JS :**\
../evc-lib/slick/slick.min.js

## Google Font

Chargement de la police Montserrat via **nouveau** code fourni par Google :\
[https://fonts.google.com/specimen/Montserrat](https://fonts.google.com/specimen/Montserrat)

voir ../evc-include/inc-head.php

```
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;1,200;1,300;1,400;1,500;1,600;1,700;1,800&display=swap">
```

## Font Awesome

Utilisation de Font Awesome Pro 5.13.1 (Juillet 2020)\
&#x20;[https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1](https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1)

**CSS :**\
../evc-lib/css/fontawesome.all.min.css => version minifiée de production

NB : Hosting Font Awesome Yourself\
[https://fontawesome.com/how-to-use/on-the-web/setup/hosting-font-awesome-yourself](https://fontawesome.com/how-to-use/on-the-web/setup/hosting-font-awesome-yourself)

## Drapeaux des pays au format SVG

répertoire ../evc-images/country-flags/svg :\
&#x20;[https://github.com/lipis/flag-icon-css/tree/master/flags/4x3](https://github.com/lipis/flag-icon-css/tree/master/flags/4x3)\
&#x20;[https://flagicons.lipis.dev/](https://flagicons.lipis.dev/)

Code des drapeaux :\
&#x20;[https://fr.wikipedia.org/wiki/ISO\_3166-1](https://fr.wikipedia.org/wiki/ISO\_3166-1)

## Input type DATE

How to make  supported on all browsers? Any alternatives?\
[https://stackoverflow.com/questions/18020950/how-to-make-input-type-date-supported-on-all-browsers-any-alternatives](https://stackoverflow.com/questions/18020950/how-to-make-input-type-date-supported-on-all-browsers-any-alternatives)

Can I use\
[https://caniuse.com/#feat=input-datetime](https://caniuse.com/#feat=input-datetime)\
\=> Safari et IE11 ne supportent pas

&#x20;[https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input/date)

[Datepicker et accessibilité](https://blog.atalan.fr/datepicker-et-accessibilite/) "noter que la balise  qui propose nativement un Datepicker n’est pas étudiée dans le cadre de cet article. Notamment car elle n’est actuellement pas supportée par les navigateurs Internet Explorer 11 et Safari 11 sous macOS. ([Support de type="date" sur le site « Can I use ».](https://caniuse.com/#search=type%3D%22date%22))"

Bootstrap v4 datepicker \[closed]\
[https://stackoverflow.com/questions/33870344/bootstrap-v4-datepicker](https://stackoverflow.com/questions/33870344/bootstrap-v4-datepicker)
