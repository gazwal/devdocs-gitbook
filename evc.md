---
description: JUIN 2020 - eVisa Center
---

# EVC

Site de DEV ici : [http://gazwal.alwaysdata.net/EVC/evc-pages](http://gazwal.alwaysdata.net/EVC/evc-pages/)

Page Pays : [http://gazwal.alwaysdata.net/EVC/evc-pages/pays.php](http://gazwal.alwaysdata.net/EVC/evc-pages/pays.php)

{% hint style="danger" %}
ATTENTION : merci de supprimer la plupart des commentaires HTML dans le code pour la mise en production ;-\)  
`<!-- Bla Bla Bla Commentaire HTML Bla Bla Bla -->`
{% endhint %}

## Librairies, CSS, JS :

Voir les fichiers :  
.**./evc-include/inc-head.php  
../evc-include/inc-footer-scripts.php**  
  
NB : toutes les pages ont le même "template" et chargent les mêmes librairies, CSS et JS

**EVC CSS :**  
\(compilée via SASS : ../sass/evc-styles.scss\)  
../evc-css/evc-styles.css =&gt; version normale non minifiée  
../evc-css/evc-styles.min.css =&gt; version minifiée de production

**EVC JS :**  
../evc-js/evc.js

## jQuery

Utilisation de jQuery 3.5.1 comme recommandé dans la doc Bootstrap 4.5.x :  
[https://getbootstrap.com/docs/4.5/getting-started/introduction/\#js](https://getbootstrap.com/docs/4.5/getting-started/introduction/#js)  
**JS :**  
../evc-lib/js/jquery-3.5.1.min.js =&gt; version minifiée de production

## Bootstrap

 Utilisation de la dernière version de Bootstrap =&gt; 4.5.0 \(Juillet 2020\)  
 [https://getbootstrap.com/docs/4.5/getting-started/introduction/](https://getbootstrap.com/docs/4.5/getting-started/introduction/)

**CSS :**  
\(compilée via SASS : ../sass/bootstrap.scss\)  
****../evc-css/bootstrap.css =&gt; version normale non minifiée  
../evc-css/bootstrap.min.css =&gt; version minifiée de production

**JS :** utilisation de **bootstrap.bundle.min.js** qui inclus Popper.js  
\(requis pour utiliser bootstrap-select\)  
../evc-lib/js/bootstrap.bundle.min.js =&gt; version minifiée de production

## Bootstrap-Select

Permet la re-écriture des SELECT via javascript; et rajoute de nombreuses fonctionnalités, à explorer :  
[https://developer.snapappointments.com/bootstrap-select/](https://developer.snapappointments.com/bootstrap-select/)

**demo /exemples :**  
 [https://developer.snapappointments.com/bootstrap-select/examples/](https://developer.snapappointments.com/bootstrap-select/examples/)  
 [https://thdoan.github.io/bootstrap-select/examples.html](https://thdoan.github.io/bootstrap-select/examples.html)

**Permet aussi de mettre des drapeaux SVG dans les SELECT** =&gt; mon code utilise l'attribut data-content="" pour mettre les images, voir ici aussi :  
 [https://developer.snapappointments.com/bootstrap-select/examples/\#custom-content](https://developer.snapappointments.com/bootstrap-select/examples/#custom-content)  
 [https://github.com/snapappointments/bootstrap-select-temp/issues/18](https://github.com/snapappointments/bootstrap-select-temp/issues/18)

**CSS :**  
\(compilée via SASS : ../sass/bootstrap-select.scss\)  
****../evc-css/bootstrap-select.css =&gt; version normale non minifiée  
../evc-css/bootstrap-select.min.css =&gt; version minifiée de production

**JS :**  
../evc-lib/js/bootstrap-select.min.js =&gt; version minifiée de production

## Slick carousel

{% embed url="https://kenwheeler.github.io/slick/" %}

Utilisé pour le carousel / slider :  
- en page d'accueil =&gt; section.home-01  
- dans le sidebar =&gt; ../evc-include/inc-aside-page-pays.php

**CSS :**  
\(compilée via SASS : ../sass/slick.scss + ../sass/slick-theme.scss\)  
  
****../evc-css/slick.css =&gt; version normale non minifiée  
../evc-css/slick.min.css =&gt; version minifiée de production

../evc-css/slick-theme.css =&gt; version normale non minifiée  
../evc-css/slick-theme.min.css =&gt; version minifiée de production

**JS :**  
../evc-lib/slick/slick.min.js

## Google Font

Chargement de la police Montserrat via **nouveau** code fourni par Google :  
[https://fonts.google.com/specimen/Montserrat](https://fonts.google.com/specimen/Montserrat)

voir ../evc-include/inc-head.php

```text
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,200;0,300;0,400;0,500;0,600;0,700;0,800;1,200;1,300;1,400;1,500;1,600;1,700;1,800&display=swap">
```

## Font Awesome

Utilisation de Font Awesome Pro 5.13.1 \(Juillet 2020\)  
 [https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1](https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1)

**CSS :**  
../evc-lib/css/fontawesome.all.min.css =&gt; version minifiée de production

NB : Hosting Font Awesome Yourself  
[https://fontawesome.com/how-to-use/on-the-web/setup/hosting-font-awesome-yourself](https://fontawesome.com/how-to-use/on-the-web/setup/hosting-font-awesome-yourself)

## Drapeaux des pays au format SVG

répertoire ../evc-images/country-flags/svg :  
 [https://github.com/lipis/flag-icon-css/tree/master/flags/4x3](https://github.com/lipis/flag-icon-css/tree/master/flags/4x3)  
 [https://flagicons.lipis.dev/](https://flagicons.lipis.dev/)

Code des drapeaux :  
 [https://fr.wikipedia.org/wiki/ISO\_3166-1](https://fr.wikipedia.org/wiki/ISO_3166-1)

