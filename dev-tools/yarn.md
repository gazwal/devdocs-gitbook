---
description: Fast, reliable, and secure dependency management.
---

# Yarn

yarn est installé & géré par [Homebrew](homebrew.md)\
_You can install Yarn through the_ [_Homebrew package manager_](https://brew.sh/)_. This will also install Node.js if it is not already installed._

Docs :\
[https://yarnpkg.com/en/docs/install#mac-stable](https://yarnpkg.com/en/docs/install#mac-stable)\
[https://yarnpkg.com/en/docs/cli/](https://yarnpkg.com/en/docs/cli/)\


{% hint style="danger" %}
Mettre à jour Yarn => passer par Homebrew !!

```
$ brew upgrade yarn
```
{% endhint %}

```
// Voir sa version de Yarn
$ yarn -v

// Créer un package.json
$ yarn init

//oubien pour éviter les questions interactives (--yes or -Y)
$ yarn init --yes

// Ajouter un paquet en devDependencies (--dev or -D)
$ yarn add webpack --dev

// Ajouter une version spécifique
$ yarn add susy@2.2.14 --exact --dev

// Ajouter un paquet Github public
// voir https://oncletom.io/node.js/chapter-05/
// https://docs.npmjs.com/files/package.json#git-urls-as-dependencies
$ yarn add https://github.com/vmitsaras/js-offcanvas.git
$ yarn add https://github.com/FrDH/mmenu-js.git#8.4.3

// Lister les paquets NON à jour
$ yarn outdated

// Lister tous les paquets de "premier niveau"
$ yarn list --depth=0

// Lister/filtrer les paquets ayant le mot "gulp" dans leur nom
$ yarn list --pattern gulp

// Lister/filtrer les paquets ayant le mot "sass" dans leur nom
$ yarn list --pattern sass --depth=0
yarn list v1.22.10
├─ breakpoint-sass@2.7.1
├─ gulp-sass-partials-imported@1.0.7
├─ gulp-sass@4.1.1
├─ node-sass@4.14.1
└─ sass-graph@2.2.6
✨  Done in 0.42s.

// installer les paquets via le packages.json
$ yarn install

// mettre à jour un paquet
// (pas de maj de package.json)
// gulp-sass    4.0.2   4.1.0  4.1.0
$ yarn upgrade gulp-sass

// mettre à jour tous les paquets
$ yarn upgrade

// Mettre à jour un paquet à sa dernière version
// (ça outrepasse le premier chiffre de version)
// (pas de maj de package.json)
// gulp-autoprefixer 6.1.0   6.1.0  7.0.1
$ yarn upgrade gulp-autoprefixer --latest

//
```

Problème de mise à jour du package.json :\
[Why Running \`yarn upgrade\` Does Not Update My \`package.json\`](https://dev.to/wgao19/why-running-yarn-upgrade-does-not-update-my-package-json-3mon)
