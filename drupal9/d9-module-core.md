# Module Core

Liste des modules CORE installés par défaut lors d'une install "**standard**" :

```text
robin@mbprobin drupal9-composer % drush pm-list --type=Module --status=enabled --core   
 -------------- -------------------------------------------------- --------- --------- 
  Package        Name                                               Status    Version  
 -------------- -------------------------------------------------- --------- --------- 
  Core           Automated Cron (automated_cron)                    Enabled   9.1.10   
  Core           BigPipe (big_pipe)                                 Enabled   9.1.10   
  Core           Block (block)                                      Enabled   9.1.10   
  Core           Custom Block (block_content)                       Enabled   9.1.10   
  Core           Breakpoint (breakpoint)                            Enabled   9.1.10   
  Core           CKEditor (ckeditor)                                Enabled   9.1.10   
  Core           Color (color)                                      Enabled   9.1.10   
  Core           Comment (comment)                                  Enabled   9.1.10   
  Core           Configuration Manager (config)                     Enabled   9.1.10   
  Core           Contact (contact)                                  Enabled   9.1.10   
  Core           Contextual Links (contextual)                      Enabled   9.1.10   
  Field types    Datetime (datetime)                                Enabled   9.1.10   
  Core           Database Logging (dblog)                           Enabled   9.1.10   
  Core           Internal Dynamic Page Cache (dynamic_page_cache)   Enabled   9.1.10   
  Core           Text Editor (editor)                               Enabled   9.1.10   
  Core           Field (field)                                      Enabled   9.1.10   
  Core           Field UI (field_ui)                                Enabled   9.1.10   
  Field types    File (file)                                        Enabled   9.1.10   
  Core           Filter (filter)                                    Enabled   9.1.10   
  Core           History (history)                                  Enabled   9.1.10   
  Field types    Image (image)                                      Enabled   9.1.10   
  Multilingual   Language (language)                                Enabled   9.1.10   
  Field types    Link (link)                                        Enabled   9.1.10   
  Core           Custom Menu Links (menu_link_content)              Enabled   9.1.10   
  Core           Menu UI (menu_ui)                                  Enabled   9.1.10   
  Core           Node (node)                                        Enabled   9.1.10   
  Field types    Options (options)                                  Enabled   9.1.10   
  Core           Internal Page Cache (page_cache)                   Enabled   9.1.10   
  Core           Path (path)                                        Enabled   9.1.10   
  Core           Path alias (path_alias)                            Enabled   9.1.10   
  Core           Quick Edit (quickedit)                             Enabled   9.1.10   
  Core           RDF (rdf)                                          Enabled   9.1.10   
  Core           Search (search)                                    Enabled   9.1.10   
  Core           Shortcut (shortcut)                                Enabled   9.1.10   
  Core           System (system)                                    Enabled   9.1.10   
  Core           Taxonomy (taxonomy)                                Enabled   9.1.10   
  Field types    Text (text)                                        Enabled   9.1.10   
  Core           Toolbar (toolbar)                                  Enabled   9.1.10   
  Core           Tour (tour)                                        Enabled   9.1.10   
  Core           Update Manager (update)                            Enabled   9.1.10   
  Core           User (user)                                        Enabled   9.1.10   
  Core           Views (views)                                      Enabled   9.1.10   
  Core           Views UI (views_ui)                                Enabled   9.1.10   
 -------------- -------------------------------------------------- --------- --------- 
```

## Module core à désinstaller

... au besoin ... suite à une installation "standard" :

* **Quick Edit** : Modification rapide du contenu.
* **Help** : Gère l'affichage de l'aide en ligne.

## Module core à installer

... au besoin ... suite à une installation "standard" :

* Responsive Image : Fournit un formateur d'image et une cartographie des points de rupture pour afficher des images adaptatives en utilisant l'élément HTML5 picture.

## breakpoint

{% hint style="warning" %}
Please note that inputting your CSS breakpoints into your breakpoints.yml file is only necessary when Drupal needs to interact with the breakpoints as in the case of the [Responsive Images module](https://www.drupal.org/docs/8/mobile-guide/responsive-images-in-drupal-8).
{% endhint %}

[Working with breakpoints in Drupal 8](https://www.drupal.org/docs/8/theming-drupal-8/working-with-breakpoints-in-drupal-8)



