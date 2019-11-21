# Theming

## Debug

[Printer des variables avec KINT](https://www.webwash.net/how-to-print-variables-using-kint-in-drupal-8/) \(activer Devel + Devel Kint\)  
kint\(\) =&gt; The kint function prints everything at the top of the page.  
ksm\(\) =&gt; The ksm function prints the Kint output in the message region of your theme.

Utilisation avec Twig =&gt; `{{ kint(page) }`

{% hint style="info" %}
You must turn on Twig debugging for the `{{ kint() }}` function to render. Read [this page](https://www.drupal.org/node/1906392) on drupal.org to learn how.
{% endhint %}

