# MAMP

## Adding New Versions of PHP to MAMP

{% embed url="https://stackoverflow.com/questions/72380752/macos-mamp-and-php-8-1" %}

{% embed url="https://gist.github.com/codeadamca/09efb674f54172cbee887f04f700fe7c" %}

### Important :

Ci-dessus => le point 4 ne fonctionne pas, c'est pas le bon endroit pour chopper le dossier MODULES, en fait tout est déjà dedans le dossier du PHP :\
ce qui à fonctionner c'est cette réponse => [https://stackoverflow.com/a/73228670](https://stackoverflow.com/a/73228670)

```
Copy
/usr/local/Cellar/php/8.<version_number>/lib/httpd/modules/libphp.so 
to
/Applications/MAMP/bin/php/php8.<version_number>/modules/libphp.so

Donc en fait, /httpd/modules du dossier httpd pour le mettre
à la racine du PHP dans MAMP
=> voir, par exemple, /Applications/MAMP/bin/php/php8.1.13
```

