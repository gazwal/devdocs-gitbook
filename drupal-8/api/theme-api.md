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

