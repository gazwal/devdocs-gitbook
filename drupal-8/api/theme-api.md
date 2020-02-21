# Theme API

## hook\_page\_attachments <a id="page-subtitle"></a>

[Drupal 8: \#attached - Part 1](https://www.axelerant.com/resources/team-blog/drupal-8-attached-part-1)  
[Drupal 8: \#attached - Part 2](https://www.axelerant.com/resources/team-blog/drupal-8-attached-part-2)

{% hint style="danger" %}
On ne peut implémenter de `hook_page_attachments()` que dans un **module**. Dans un **thème** il faudra préférer `hook_page_attachments_alter()` qui fonctionne à peu près de la même manière.
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
// From core/modules/contextual/contextual.module.
function contextual_page_attachments(array &$page)
{
  if (!\Drupal::currentUser()->hasPermission('access contextual links')) {
    return;
  }

  $page['#attached']['library'][] = 'contextual/drupal.contextual-links';
}
```

```php
/**
 * Implements hook_page_attachments().
 */
function gazwal_utils_page_attachments(array &$attachments)
{
  $attachments['#attached']['library'][] = 'gazwal_utils/js-offcanvas';
}
```

