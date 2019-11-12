# Objet Window

```javascript
(function () { // fonction qui s'auto éxécute
// pour évité d'avoir des conflits avec variables identiques

  // javascript va définir une variable globale !!
  // elle va être automatiquement propriété de l'objet Window
  c = "Demo C"
  console.log(window.c)
  
  // si on met un VAR, la variable n'est dispo que dans la fonction
  // et ne sera pas propriété de l'objet Window
  var a = "Demo A"
  console.log(window.a) // undefined
  console.log(a) // Demo A

}) () // fonction qui s'auto éxécute

```

```javascript
window.alert("Salut les gens")
// La fonction alert bloque l'exécution du script

var demo = window.prompt("Salut les gens")
console.log(demo)

var demo = window.confirm("Salut les gens")
console.log(demo) // true ou false
```

```javascript
(function () {

var demo = function () {
  console.log("Demo")
}
// window.setInterval() prend une fonction en paramètre
// le code s'éxécute à l'infinie :
window.setInterval(demo, 1000)
// le code s'éxécute une seul fois :
window.setTimeout(demo, 1000)


// On peut écrire la même chose avec un callback
// callback = des fonctions qui sont passées en paramètre
var i = 0
var timer = window.setInterval(function () {
  i++
  // le script va s'arrêter au bout de 10s
  if (i === 3) {
    window.clearInterval(timer)
  }
  console.log(i)
}, 1000)
console.log("Blabla")


}) ()


```

