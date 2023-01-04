---
description: Le gestionnaire de paquets pour macOS
---

# Homebrew

{% embed url="https://brew.sh/index_fr" %}

Homebrew installe [ce dont vous avez besoin](https://formulae.brew.sh/formula/) et qu’Apple n’a pas installé.\
Homebrew installe les paquets dans leurs propres répertoires et crée des liens symboliques de leurs fichiers vers `/usr/local`.\
DOCS : [https://docs.brew.sh/](https://docs.brew.sh/)\
FAQ :  [https://docs.brew.sh/FAQ](https://docs.brew.sh/FAQ)

```
// Vérifier sa version de Homebrew
$ brew -v

// Mettre à jour HOMEBREW
$ brew update

// Lister les paquets installés
$ brew list

// Lister les paquets qui ne sont pas à jour
$ brew outdated

// Mettre à jour tous les paquets
$ brew upgrade

// Mettre à jour un paquet spécifique
$ brew upgrade <formula>
// exemple
$ brew upgrade yarn
```

#### Plein de commandes :

{% embed url="https://devhints.io/homebrew" %}



#### Docs :

{% embed url="https://stackoverflow.com/questions/28017374/what-is-the-suggested-way-to-install-brew-node-js-io-js-nvm-npm-on-os-x" %}

