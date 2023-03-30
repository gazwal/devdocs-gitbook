---
description: Exemple de MAJ de la version 6.6 vers 6.8
---

# Mettre à jour MAMP

[How to upgrade or update MAMP/MAMP Pro - Stuart Haiz](https://haizdesign.com/mamp/how-to-upgrade-mamp-pro/)

{% embed url="https://dev.to/crankysparrow/configuring-virtual-hosts-with-mamp-f3i" %}

1. Faire une copie de backup du dossier MAMP\
   /Applications/MAMP\
   le renomer MAMP\_OLD
2. Lancer l'install de la nouvelle version via le .pkg
3. Supprimer le dossier de backup créé lors de l'install\
   ex : MAMP\_2023-03-30\_18-40-48
4. Supprimer la version PRO en supprimant l'app /Applications/MAMP PRO.app
5. lancer l'install fraichement installée /Applications/MAMP/MAMP.app
6. configurer les infos\
   \=> ports sur 80 & 3306\
   \=> document ROOT sur WWW\
   Tout est déjà OK, et il active par défaut PHP7.4.33 et PHP8.2
7.  Activer le **httpd-vhosts.conf** via le\
    /Applications/MAMP/conf/apache/httpd.conf

    \=> [https://dev.to/crankysparrow/configuring-virtual-hosts-with-mamp-f3i](https://dev.to/crankysparrow/configuring-virtual-hosts-with-mamp-f3i)

    ```
    # Virtual hosts
    Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf
    ```
8. Récupérer en copier/coller les infos de tous les VHosts de\
   /Applications/MAMP\_OLD/conf/apache/extra/httpd-vhosts.conf\
   vers\
   /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf
9. Relancer MAMP, tout est OK

\
