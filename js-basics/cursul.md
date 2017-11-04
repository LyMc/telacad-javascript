```html
<!doctype html>
<html lang="ro">
<head>
	<meta charset="utf-8">
	<title>JS Basics</title>
	<script src="script.js"></script>
</head>
<body>

</body>
</html>
```

```js
/* eslint-disable */

// Variabile primitive

var course = 'JavaScript'
var courseNumber = 3
var courseDescription = 'JavaScript basics'

var string = 'Sir de caractere'
var number = 10
var float = 3.1415
var notANumber = NaN
var boolean = false
var stringFalse = 'false'
var intelegDespreCeVorbesti = true
var cevGol = null
var amUitatVariabila = undefined
var numarPixuriInSuport = 10

/*
var a = 1
var b = 2
var sum = a + b
var mul = a * (b + 2) / 10
*/
var a = 1,
	b, sum, mul

b = 2
sum = a + b
mul = a * (b + 2) / 10

a = a + 2
//console.log('prima adunare', a)
// debugger
a += 2
//console.log('a doua adunare', a)

a -= 1
a *= 1
a /= 1

// console.log('modul', 93%10)

var c, d
c = 'Salut '
d = 'prietene'
var salutare = c + d

var arTrebuiSaFieNumar = '3.56pi'
var acumChiarEsteNumar = +arTrebuiSaFieNumar
var oMetodaDeAFaceUnInt = parseInt(arTrebuiSaFieNumar)
var sumaNumarSiCaracter = a + acumChiarEsteNumar
var difNumarSiCaracter = a - arTrebuiSaFieNumar

// Operatorii logici
var adevar = true
var fals = false
var nuEAdevar = !adevar
var ambeleAdevaruri = adevar && false
var unulDinAdevaruri = adevar || false

if (a === '4') {
	console.log('adevarat', typeof a)
} else {
	console.log('fals', typeof a)
}

// var multime = new Array()
var multime = []
var suportPixuri = ['rosu', 'negru', 'albastru', 4, 5, 6]

// proprietati
var numarPixuri = suportPixuri.length

// metode
console.log('valoare initiala', suportPixuri)

//suportPixuri.reverse()
//suportPixuri.shift()
//suportPixuri.unshift(1, 2)
//suportPixuri.pop()
//suportPixuri.push(1, 5)
//suportPixuri.splice(3, 2)
//var arrayNou = suportPixuri.slice()
//arrayNou[1] = 'alb'
//var oBucataDeArray = suportPixuri.slice()

//var indice = suportPixuri.indexOf('negru')

//console.log('valoare finala', suportPixuri[indice])
//console.log('indice', indice)

var arrayCaSiString = suportPixuri.join(', ')

console.log('arrayCaSiString', arrayCaSiString)
```
