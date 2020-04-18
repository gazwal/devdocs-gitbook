# Theme API

## hook\_page\_attachments <a id="page-subtitle"></a>

Add attachments \(typically assets\) to a page before it is rendered.  
API =&gt; [function hook\_page\_attachments](https://api.drupal.org/api/drupal/core%21lib%21Drupal%21Core%21Render%21theme.api.php/function/hook_page_attachments/8.2.x)

[Drupal 8: \#attached - Part 1](https://www.axelerant.com/resources/team-blog/drupal-8-attached-part-1)  
[Drupal 8: \#attached - Part 2](https://www.axelerant.com/resources/team-blog/drupal-8-attached-part-2)

{% hint style="danger" %}
On ne peut implémenter de `hook_page_attachments()` que dans un **module**. Dans un **thème** il faudra préférer`hook_page_attachments_alter()` qui fonctionne à peu près de la même manière.
{% endhint %}

```php
/**
 * Implements hook_page_attachments().
 */
function module_name_page_attachments(array &$page) {
  $description = [
    '#tag' => 'meta',
    '#attributes' => [
      'name' => 'description',
      'content' => 'This is my website.',
    ],
  ];
  $page['#attached']['html_head'][] = [$description, 'description'];
}
```

```php
// exemple Inline JavaScript that affects the entire page
// Inline JavaScript is highly discouraged !!
function fluffiness_page_attachments(array &$attachments)
{
  $attachments['#attached']['html_head'][] = [
    // The data.
    [
      '#type' => 'html_tag',
      // The HTML tag to add, in this case a  tag.
      '#tag' => 'script',
      // The value of the HTML tag, here we want to end up with
      // alert("Hello world!");.
      '#value' => 'alert("Hello world!");',
      // Set attributes like src to load a file.
      '#attributes' => array('src' => ''),

    ],
    // A key, to make it possible to recognize this HTML element when altering.
    'hello-world',
  ];
}
```

`hook_page_attachments()` permet aussi d'attacher des librairies, voir [Adding stylesheets \(CSS\) and JavaScript \(JS\) to a Drupal 8 module](https://www.drupal.org/docs/8/creating-custom-modules/adding-stylesheets-css-and-javascript-js-to-a-drupal-8-module)

```php
// exemple dans l'API drupal
function hook_page_attachments(array &$attachments)
{
  // Unconditionally attach an asset to the page.
  $attachments['#attached']['library'][] = 'core/domready';

  // Conditionally attach an asset to the page.
  if (!\Drupal::currentUser()->hasPermission('may pet kittens')) {
    $attachments['#attached']['library'][] = 'core/jquery';
  }
}
```

```php
// exemple dans module custom
/**
 * Implements hook_page_attachments().
 */
function gazwal_utils_page_attachments(array &$attachments)
{
  $attachments['#attached']['library'][] = 'gazwal_utils/js-offcanvas';
}
```

```php
// exemple dans module custom
/**
 * Implements hook_page_attachments().
 */
function mymodule_page_attachments(array &$page) {
  $config = \Drupal::config('mymodule.settings');
  $apiKey = $config->get('google_map_api_key');
  $page['#attached']['html_head'][] = [
    [
      '#type' => 'html_tag',
      '#tag'  => 'script',
      '#attributes' => ['src' => "//maps.googleapis.com/maps/api/js?key=$apiKey"],
    ],
    'mymodule_google_map_lib',
  ];
}
```

