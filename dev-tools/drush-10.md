# Drush 10

DOCS :

{% embed url="https://docs.alphanodes.com/drush/drush10.html" %}

## Drush + MAMP

[**Working witrh Drush on  MAMP**](https://www.drupal.org/node/1651282)\*\*\*\*

Problèmes de connxion SQL avec Drush : SQLSTATE\[HY000\] \[2002\] No such file or directory :

* [J'ai \`PDOException: SQLSTATE \[HY000\] \[2002\] Aucun fichier ou répertoire de ce type\` lors de l'utilisation de drush \[fermé\]](https://qastack.fr/drupal/99446/ive-got-pdoexception-sqlstatehy000-2002-no-such-file-or-directory-when-u)
* [https://www.drupal.org/node/1651282](https://www.drupal.org/node/1651282)

La solution rapide qui à fonctionné du premier coup pour moi, sur projet DRUPAL 9 : 

```text
Rajout de la ligne :
'unix_socket' => '/Applications/MAMP/tmp/mysql/mysql.sock'
dans le /web/sites/default/settings.local.php :
//
$databases['default']['default'] = array (
  'database' => 'xxs_urban-elab',
  'username' => 'root',
  'password' => 'root',
  'prefix' => '',
  'host' => 'localhost',
  'port' => '3306',
  'namespace' => 'Drupal\\Core\\Database\\Driver\\mysql',
  'driver' => 'mysql',
  'unix_socket' => '/Applications/MAMP/tmp/mysql/mysql.sock'
);

```

## Commandes

```text
// An overview of the environment
drush status

// drush cache-rebuild
drush cr
```

