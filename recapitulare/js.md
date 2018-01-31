# Recapitulare JS

### Inițializare

Din cauza felului în care rulează JS-ul în browser, o practică bună e să așteptăm până pagina este complet încărcată, și abia apoi să rulăm codul nostru:
```js
window.addEventListener('load', function() {
    // vom scrie codul în această funcție
})
```

### Pregătim elementele cu care vom lucra
Pentru a selecta un element din pagină, ne folosim de DOM, pentru a selecta primul element ce conține clasa startButton:
```js
const startButtonElement = document.querySelector('.startButton')
```
dacă avem un input cu clasa taskName, vom putea citi valoarea lui folosind această referință:
```js
const taskNameElement = document.querySelector('.taskName')
```
pentru a citi valoarea unui input:
```js
let taskName = taskNameElement.value
```
! atenție, vom primi ceea ce a scris utilizatorul în momentul când vom citi această valoare, de aceea, e bine să o facem la după o anumită acțiune (de ex. la click pe un buton).

pentru a urmări o acțiune vom folosi `addEventListener`, pentru a urmări acțiunea de `click`:
```js
startButtonElement.addEventListener('click', function() {
    let taskName = taskNameElement.value
    console.log(taskName)
})
```
astfel, vom citi exact ceea ce a scris utilizatorul în câmpul nostru înainte să dea click pe buton. Dacă dorim să folosim `taskName` în alte funcții, atunci îl definim în afara funcției, și-l suprascriem la click:
```js
let taskName
startButtonElement.addEventListener('click', function() {
    taskName = taskNameElement.value
})
```

### Manipularea timpului
timpul în JS este păstrat printr-un număr de milisecunde ce au trecut din 1970 (se primește un număr de 13 cifre), pentru a afla milisecunda curentă:
```js
const exactTime = new Date()
```
`new Date()` ne va întoarce un obiect de tip `Date`, care are o valoare și câteva metode de manipulare al timpului, salvând acest obiect în variabila `exactTime`, putem să o folosim mai târziu pentru a ști momentul exact când am creat această variabilă.

Câteva metode de a citi o parte din dată / oră:
```js
const timestamp = exactTime.getTime() // ex. 1517437645516
const hours = exactTime.getHours() // ora curentă (0-23)
const year = exactTime.getFullYear() // ex. 2018
const minutes = exactTime.getMinutes()
const seconds = exactTime.getSeconds()
const miliseconds = exactTime.getMilliseconds() // (0-999)
```
referința cu toate metodele poate fi găsită [aici](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date).

Uneori, avem nevoie să facem diferența dintre două momente de timp. Putem face aceasta foarte simplu datorită faptului că timpul e simplu număr:
```js
const dif = new Date() - exactTime
```
astfel, în `dif` vom primi diferența de milisecunde dintre momentul când am aflat `exactTime` și acum.
Acum, putem ușor face calcule necesare pentru a afla valori parțiale (secunde, minute, ore, zile, ani...):
```js
const sec = (dif / 1000) % 60
const min = (dif / (60 * 1000)) % 60
const h = (dif / (60 * 60 * 1000))
console.log('Au trecut ' + h + ':' + min + ':' + sec + ' de la ...') 
```
După cum se vede, sunt doar câteva operații matematice simple.
Operatorul `%` modulo întoarce restul de la împărțire (ex. `13 % 3 = 1`, `13 = 4 * 3 + 1`)

Dacă dorim să facem un timer și să afișăm cât timp a trecut de la un moment anume, putem crea o funcție care să ne întoarcă această valoare:
```js
function calcDif(fromTime) {
    const dif = new Date - fromTime
    const sec = (dif / 1000) % 60
    const min = (dif / (60 * 1000)) % 60
    const h = (dif / (60 * 60 * 1000))
    return h + ':' + min + ':' + sec 
}
```
Pentru a folosi funcția:
```js
const fixedTime = new Date('2018-02-01 01:00')
console.log('Au trecut ' + calcDif(fixedTime) + ' de la ...')
```
în acest exemplu am inițializat obiectul de tip `Date` cu o valoare, astfel, zicândui momentul care ne interesează.
Având această funcție, putem crea ușor un timer:
```js
const timerElement = document.querySelector('.timer')
const startTime = new Date()
let timerRef = setInterval(function() {
    timerElement.innerHTML = calcDif(startTime)
}, 1000)
```
câteva clarificări:
`timerElement` este orice element html în care să afișăm un text ceva (dacă e input, se schimbă valoarea lui, nu html-ul), de ex. un div, aici vom afișa cât timp a trecut
`setInterval` este o metodă care va apela o funcție la intervalul setat în milisecunde (în cazul nostru, la fiecare 1000ms === 1s)
`innerHTML` ne permite să citim sau să modificăm html-ul unui element, în cazul nostru vom scrie în el cât timp a trecut.

Dacă am pornit un timer, ar fi bine să-l și oprim, pentru aceasta ne vom folosi de referința intervalului, care e returnată la inițializare:
```js
stopButton.addEventListener('click', function() {
    clearInterval(timerRef)
})
```
