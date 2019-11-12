# Les bases

DOC [  
https://developer.mozilla.org/fr/docs/Web/JavaScript](https://developer.mozilla.org/fr/docs/Web/JavaScript)  
[https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Instructions/while)

## Variables

```javascript
var demo = 2
var demo = 2,5
var demo = -6

// chaîne de caractère, guillemet simple ou double
var demo = "Hello"
var demo = 'Hello'
// console
demo
"Hello"

// bool
var a = false
var b = true

// NB : on met pas de $ devant comme en PHP
// NB : pas besoin de mettre de ; à la fin de notre instruction
// NB : une variable prend par défaut la valeure "undefined" = Hoisting

var demo = "Salut"
demo = "Hello" // ATTENTION, ici on modifie la valeur de demo
// console

"Hello"
```

{% hint style="warning" %}
on ne peut pas déclarer une variable avec un chiffre ou un caractère spécial  
var 01 = "hello"
{% endhint %}

## Opérations simples

{% tabs %}
{% tab title="" %}
```javascript
// javascript est un language faiblement typé
3 + 4 // 7
"3" + 4 // "34"
"3" * 4 // 12
"3" * "3" // 9
"Salut les gens" * 4 // NaN (Not a Number)
```
{% endtab %}
{% endtabs %}

## Tableau

```javascript
var eleves = ["Jean", "John", "Marion"]
eleves[0] // "Jean"
eleves[1] // "John"
eleves[2] // "Marion"

// NB : l'index commence à 0, comme en PHP
```

{% hint style="warning" %}
On peut créer un tableau qui contient des objets :  
Pas de tableau associatifs en JavaScript comme en PHP \(_key =&gt; value_\)  
Il faut pour cela créer des objets \(avec des accolades\)  
Pour parcourir un tableau avec des key=&gt;value avec la boucle FOR on fait souvent des tableau avec des objets dedans.  
Voir exercices ci-dessous \(boucles\)  
**TOUT est objet dans javascript !**
{% endhint %}

## Objet

```javascript
eleve = {nom: "Marc", age: 12, moyenne: 15}
eleve.nom // "Marc"
eleve.age // 12
eleve.moyenne // 15

On peut aussi écrire avec la même syntaxe que les tableau (déconseillé)
eleve["age"] // 12
eleve['age'] // 12
```

On peut définir à la volée de nouvelles propriétés pour notre objet

```javascript
// console
eleve.taille = 140
140

// on affiche la valeur de l'objet eleve
eleve
Object { nom: "Marc", age: 12, moyenne: 15, taille: 140 }
```

## Conditions / Comparaisons

```javascript
var marc = {
  nom: "Marc",
  age: 14,
  moyenne: 15
}

// comme en PHP, attention au esle if (elseif en PHP)
// on a aussi les for, while, foreach, switch case, etc .... comme PHP

if (marc.age >= 18) {
  console.log("Tu peux passer ton permis !")
} else if (marc.age >= 15) {
  console.log("Tu peux passer la conduite accompagnée !")
} else {
  console.log("Tu ne peux pas conduire !")
}

if (marc.age >= 18 && marc.age <= 25) {
  console.log("Bravo, tu as le droit au tarif jeune !")
} else {
  console.log("Vous n'avez pas accès au tarif jeune !")
}

if (marc.age === 18) {
  console.log("Bravo, tu as 18 ans !")
}
```

## Boucles

```javascript
// boucles "tant que"
var i = 0
while (i < 11) {
  console.log(i)
  // on incrémente i
  i = i + 1
  // i += 1
  // i++
}

// boucle "pour"
// for (valeure initiale; la condition; incrémentation)
for (var j = 0; j < 11; j++) {
  console.log(j)
}

// parcourir un tableau
var eleves = ["Jean", "John", "Marion"]
// eleves.length => taille du tableau = 3 dans notre exemple
for (index = 0; index < eleves.length; index++) {
  console.log("Bonjour " + eleves[index])
}
```

**Exercice : savoir si un nombre est premier**  
Un nombre EST premier s'il est divisible QUE par 1 ou lui-même  
Un nombres N'EST PAS premier s'il est divisible par un nombre entre 2 et \(lui-même -1\)

{% hint style="info" %}
on utilise la fonction [modulo](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Op%C3%A9rateurs/Op%C3%A9rateurs_arithm%C3%A9tiques#Reste_%28%29) = le reste de la division  
souvent utilisé pour savoir si un nombre est pair ou impair
{% endhint %}

```javascript
var nombre = 31
var estPremier = true

for (var index = 2; index < nombre; index++) {
  // si le nombre est divisible (modulo === 0)
  if (nombre % index === 0) {
    estPremier = false
    console.log("Ce nombre n'est pas premier")
    console.log(nombre + " est divisible par " + index)
    break
  }
}
if (estPremier) {
  console.log(nombre + " est premier")
}
```

Exercice : Détecter les élèves qui n'ont pas la moyenne

```javascript
// Détecter les élèves qui n'ont pas la moyenne
// NB : ici on a des objets dans un tableau
var eleves = [{
  nom: "Marc",
  moyenne: 15
},
{
  nom: "Marion",
  moyenne: 8
},
{
  nom: "Antoine",
  moyenne: 4
}]

for (i = 0; i < eleves.length; i++) {
  // on stock chaque objet dans une variable
  var eleve = eleves[i]
  if (eleve.moyenne < 10) {
    console.log(eleve.nom + " n'a pas la  moyenne")
  } else {
    console.log(eleve.nom + " a la moyenne")
  }
}
```

## Fonctions

```javascript
// ####################################################
// Savoir si un nombre est premier
function estPremier(nombre) {
  for (var index = 2; index < nombre; index++) {
    // si le nombre est divisible (modulo === 0)
    if (nombre % index === 0) {
      return false
    }
  }
  return true
}

// console 
estPremier(33)
false
estPremier(12)
false
estPremier(3)
true

// ####################################################
// Elèves de la classe
var classA = [{
  nom: "Marc",
  moyenne: 15
},
{
  nom: "Marion",
  moyenne: 8
},
{
  nom: "Antoine",
  moyenne: 4
},
{
  nom: "Jean",
  moyenne: 14
}]

// Afficher qui a la moyenne
function afficheQuiALaMoyenne(eleves) {
  for (i = 0; i < eleves.length; i++) {
    var eleve = eleves[i]
    if (eleve.moyenne >= 10) {
      console.log(eleve.nom + " a la moyenne")
    }
  }
}
afficheQuiALaMoyenne(classA)
// Marc a la moyenne
// Jean a la moyenne

// Lister les élèves qui ont la moyenne
// Les mettres dans un tableau
var aLaMoyenne = function (eleves) {
  var moyennes = []
  for (var i = 0; i < eleves.length; i++) {
    var eleve = eleves[i]
    if (eleve.moyenne >= 10) {
      // méthode push()
      // https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/Array/push
      // on  rajoute l'élève au tableau s'il a la moyenne
      moyennes.push(eleve)
    }
  }
  return moyennes
}
console.log(aLaMoyenne(classA))

// ####################################################

```

Autre exemple de functions

```javascript
// ####################################################
var eleve1 = {
  nom: "Jean",
  notes: [15, 16, 18]
}
var eleve2 = {
  nom: "Marc",
  notes: [5, 18, 20]
}

// Savoir qui a la meilleure moyenne ?
// renvoi TRUE si eleve1 a une meilleure moyenne que eleve2

// calcul de la moyenne de 1 élève
var moyenne = function (notes) {
  var somme = 0
  for (var i = 0; i < notes.length; i++) {
   // on additionne chaque note de l'élève
   somme = somme + notes[i]
  }
  // moyenne de l'élève
  return somme / notes.length
}

// qui est meilleur ?
var estMeilleur = function (a, b) {
  return moyenne(a.notes) > moyenne(b.notes)
}
console.log(estMeilleur(eleve1, eleve2))


```

{% hint style="danger" %}
JavaScript ne vérifie pas le nombre de paramètres à passer dans la fonction.  
Si on envoi que 1 paramètre, il attribut _undefined_ aux autres  
cf ci-dessous :
{% endhint %}

```javascript
function multiplie(a, b) {
  return a * b
}

// console
multiplie(2, 4)
8
multiplie(2)
NaN
```

Deux manières de définir des fonctions :

```javascript
// A la manière PHP
// LA fonction est défini tout en haut !
estPremier(21) // Ca fonctionne !
//
function estPremier(nombre) {
  for (var index = 2; index < nombre; index++) {
    if (nombre % index === 0) {
      return false
    }
  }
  return true
}

// A la manière Javascript, en définissant une variable,
// majoritaire et courante :
estPremier(21) // ca fonctionne PAS car définit après dans le code
//
var estPremier = function (nombre) {
  for (var index = 2; index < nombre; index++) {
    if (nombre % index === 0) {
      return false
    }
  }
  return true
}
```

On peut mettre aussi des fonction dans un objet :  
Ces fonctions sont appelées des méthodes.

```javascript
// Fonction dans des objets
var pikachou = {
  crier: function () {
    console.log("PIKACHOU !!")
  },
  pleurer: function () {
    console.log("SNIF SNIF !!")
  }
}
// console
pikachou.crier() // PIKACHOU !!
pikachou.pleurer() // SNIF SNIF !!

// c'est ce qui est utilisé avec les nombreuses fonction natives de
// Javascript, exemple avec Math
Math.round(4567.66)
4568
Math.ceil(66.99)
67
```

```javascript
// NB : dans un FOR, la variable index est accessible en dehors de la
// fonction
for (var index = 2; index < 10; index++) {
....
}
console.log(index) // 10
// les variables ont une portée limitée uniquement dans le cadre
// des fonctions
```

{% hint style="success" %}
On parle de **méthode** quant c'est une fonction qui est utilisé sur un objet \(quand les objets ont des fonctions = méthode\)  
ex : [méthodes pour les chaînes de caractères](https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Objets_globaux/String)  
"azerty".toUpperCase\(\)  
"azerty".toUpperCase\(\)
{% endhint %}

## L'opérateur this

```javascript
// THIS
var eleve = {
  nom: "jean",
  present: function () {
    console.log(this) // this = eleve (objet)
    console.log(this.nom + " est présent") // this.nom = jean
  }
}
eleve.present() // jean est présent

// #############################
var eleve = {
  nom: "Bernard",
  present : function () {
    // on met this dans une variable
    // on utilise le mot SELF par convention
    var self = this
    var demo = {
      demo: function () {
        console.log(self.nom) // self.nom = Bernard
      }
    }
    // taff de la function eleve.present() :
    demo.demo() // Bernard
    console.log(this.nom + " est présent") // Bernard est présent
  }
}
eleve.present()
// Bernard
// Bernard est présent
```

## Prototype & Instance

```javascript
// prototype = les méthodes qui ne sont pas directement disponible sur l'objet "en cours"
// = utilisé en interne pour les différents type
// (nombre, objet, tableau, variables, etc ...) de base, = méthode globales
var eleve = {
  moyenne: function () {
    var somme = 0
    for (var i = 0; i < this.notes.length; i++) {
      // on additionne chaque note de l'élève
      somme = somme + this.notes[i]
    }
    // moyenne de l'élève
    return somme / this.notes.length
  },
  present: function () {
    console.log(this.nom + " est présent") // this.nom = jean
  }
}

var jean = {
  nom: "Jean",
  notes: [10, 20]
}

var marc = {
  nom: "Marc",
  notes: [20, 20, 12, 14]
}

jean.__proto__ = eleve // pour l'exemple
marc.__proto__ = eleve
// NB : __proto__ est utilisé en interne, ne JAMAIS y toucher comme ici dans le code !!
// ici c'est juste pour l'exemple

// du coup maintenant on peut faire
// console
jean.moyenne() // 16.5


// ### Comment créer un objet qui ai le prototype "eleve"
// Méthode 1
// Créer un nouvel objet qui aura comme prototype "eleve"
var marion = Object.create(eleve)
// l'objet est vide, mais on rajoute son nom et ses notes
marion.nom = "Marion"
marion.notes = [12, 14, 20]

// ############
// Méthode 2, celle à utiliser = constructeur (comme en PHP)
// On va créer une fonction qui va construire les objets
// Eleve = class en PHP
var Eleve = function (nom, notes) {
  this.nom = nom // va créer la propriété "nom"
  if (notes != undefined) {
    this.notes = notes // va créer la propriété "notes"
  }
}

// Pour rajouter une mèthode (moyenne) sur tous les objets de type "Eleve" :
// Les méthodes créées via prototype seront utilisable pour les instances

Eleve.prototype.moyenne = function () {
  if (this.notes === undefined) {
    return NaN
  }
  var somme = 0
  for (var i = 0; i < this.notes.length; i++) {
    somme = somme + this.notes[i]
  }
  return somme / this.notes.length
}

// pour rajouter une propriété sur tous les objets de type "Eleve"
Eleve.prototype.nombreDeChats = 120

// Création des objets (instances)
var jean = new Eleve("Jean Bono", [10, 20])
// jean devient un objet de type "Eleve" = une INSTANCE de l'objet "Eleve"
var marc = new Eleve("Marc Qui")
// marc devient un objet de type "Eleve" = une INSTANCE de l'objet "Eleve"


// on retrouve bien les objets créés:
console.log(jean) // Object { nom: "Jean Bono", notes: (2) […] }
console.log(marc) // Object { nom: "Marc Qui" }
console.log(jean.moyenne()) // 15
console.log(marc.nombreDeChats) // 120
console.log(jean.notes) // Array [ 10, 20 ]
```

