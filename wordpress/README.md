# Wordpress

## Config & Tips

Désactiver la mise à jour automatique + Activer le mode debug  
**Dans wp-config.php :**

```php
/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 *
 * For information on other constants that can be used for debugging,
 * visit the Codex.
 *
 * @link https://codex.wordpress.org/Debugging_in_WordPress
 */
define('WP_DEBUG', true);

// Désactiver les MAJ auto de worpress
define('WP_AUTO_UPDATE_CORE', false);

```



