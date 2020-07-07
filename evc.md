---
description: JUIN 2020 - eVisa Center
---

# EVC

{% hint style="danger" %}
ATTENTION : merci de supprimer la plupart des commentaires HTML lors de la mise en production ;-\)  
`<!-- Bla Bla Bla Commentaire HTML Bla Bla Bla -->`
{% endhint %}

## Librairies utilisées :





EVC : version de Bootstrap = 4.5.0  
 [https://blog.getbootstrap.com/2020/05/12/bootstrap-4-5-0/](https://blog.getbootstrap.com/2020/05/12/bootstrap-4-5-0/)  
 [https://getbootstrap.com/docs/4.5/getting-started/introduction/](https://getbootstrap.com/docs/4.5/getting-started/introduction/)  
 Les CSS sont compilées via SASS ../sass/bootstrap.scss  
 ce qui nous donne au final la feuille CSS =&gt; `../evc-css/bootstrap.min.css`  
 JS bootstrap ici =&gt; ../evc-lib/js/bootstrap.min.js

Font Awesome Pro 5.13.1  
 [https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1](https://github.com/ngdanghau/fontawesome-pro/releases/tag/5.13.1)  
 =&gt; ../evc-lib/css/fontawesome.min.css

## Drapeaux des pays au format SVG

répertoire ../evc-images/country-flags/svg :  
 [https://github.com/lipis/flag-icon-css/tree/master/flags/4x3](https://github.com/lipis/flag-icon-css/tree/master/flags/4x3)  
 [https://flagicons.lipis.dev/](https://flagicons.lipis.dev/)

Code des drapeaux :  
 [https://fr.wikipedia.org/wiki/ISO\_3166-1](https://fr.wikipedia.org/wiki/ISO_3166-1)

## Drapeaux dans DropDownList : Jquery UI Selectmenu

\(Solution testée et abandonnée\)  
 [https://jqueryui.com/selectmenu/\#custom\_render](https://jqueryui.com/selectmenu/#custom_render)  
 [https://stackoverflow.com/a/60000960](https://stackoverflow.com/a/60000960)

## Drapeaux dans DropDownList : bootstrap-select :

[https://developer.snapappointments.com/bootstrap-select/](https://developer.snapappointments.com/bootstrap-select/)  


[https://bootstrapbay.com/blog/useful-bootstrap-4-select-picker-for-your-forms/](https://bootstrapbay.com/blog/useful-bootstrap-4-select-picker-for-your-forms/)  
 [http://jsfiddle.net/pL1sncp5/](http://jsfiddle.net/pL1sncp5/)

demo /exemples :  
 [https://developer.snapappointments.com/bootstrap-select/examples/](https://developer.snapappointments.com/bootstrap-select/examples/)  
 [https://thdoan.github.io/bootstrap-select/examples.html](https://thdoan.github.io/bootstrap-select/examples.html)  


mon code utilise l'attribut data-content="" pour mettre les images :  
 [https://developer.snapappointments.com/bootstrap-select/examples/\#custom-content](https://developer.snapappointments.com/bootstrap-select/examples/#custom-content)  
 [https://github.com/snapappointments/bootstrap-select-temp/issues/18](https://github.com/snapappointments/bootstrap-select-temp/issues/18)  


## Popup

jQuery Popup Overlay  
 [https://dev.vast.com/jquery-popup-overlay/](https://dev.vast.com/jquery-popup-overlay/)  


