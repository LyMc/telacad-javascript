# JS Basics - Structura

* [Despre curs](#despre-curs)
* [Temele](#temele)
* [Introducere](#introducere)
* [Date și operații primitive](#date-și-operații-primitive)
* [Funcții și obiecte](#funcții-și-obiecte)
* [DOM](#dom)

## Despre curs

* Platforma nouă, cum ne ajută să ne organizăm
* Punctajul - tema este compusă din partea practică și teoretică \(cursant.telacad.ro\)
* [https://externos.io/](https://externos.io/)

---

## Temele

* Greșeli des întâlnite
  * &lt;/tag&gt;
  * label for
  * input submit
  * spații în atribute
  * html este despre conținut \(bgcolor, align\) &lt;font&gt;
  * identarea
  * &lt;br&gt; &lt;/br&gt; &lt;li&gt;&lt;/li&gt;&lt;br&gt;
  * form action method
  * a target
  * ul &gt; li
* Soluții

```html
<div>
    <label for="nume">
        Deschide menu
    </label>
    <input id="nume" type="checkbox" class="checkbox">
    <div class="menu">Acesta este meniul meu.</div>

    <a href="screenshots" target="_blank">Deschide screenshots</a>
</div>

<form action="http://www.telacad.ro" method="post">
    <input type="text" value="telacad" name="from">
    <button type="submit"><strong>Trimite</strong></button>
</form>
```

```css
.menu {
	display: none;
}
.checkbox:checked + .menu {
	display: block;
}
.checkbox {
	opacity: 0;
}
```

---

## Introducere

* Ce este JS?
* Ce este Java?
* Confuzii de nume
* 5.1 \(2011\)
* Editor, Browser
* Metode de a scrie JS
  * Consola
  * Inline
  * External
    * async, defer, http2
    
+ Shortcuts:
 + F12
 + Ctrl + Shift + i
 + Ctrl + Shift + j

### Specificații importante în JS

* Case Sensitive
* camelCase
* Spațiile albe
* punct și virgulă

---

## Date și operații primitive

### Variabile

### Tipuri de date

* Numere \(int, float\)
* Caractere \("'\)
* Boolean
* null
* undefined
* Symbol
* typeof

### Operatori

### Operații cu numere și caractere

### Logica

* Afirmații logice \(bool\)
* Condiționarea \(if\)
* Operatori logici \(&& \|\| :?\)

### Mulțimi

* Sintaxă
* Proprietăți
* Metode
  * reverse\(\)
  * shift\(\)
  * unshift\('a', 'b'\)
  * pop\(\)
  * push\('a', 'b'\)
  * splice\(pos, nr\)
  * = slice\(begin, start\)
  * indexOf\('a', nr\)
  * join\(sep\)

---

## Funcții și obiecte

### Funcții definite

* \(\) {}
* Argumente
* Întoarcerea unei valori

### Funcții anonime

### Immediately Invoked Functional expressions

### Variable scope

### let și const

### Obiecte

* new Object\(\)
* {}
* method
* constructor
* . vs \[\]

### Closures

funcție în funcție

---

## DOM

### Selecția în CSS

### Arborele DOM

### Proprietăți

* body
* title
* URL

### Metode

* id, class, tag, querySA
* innerHTML
* outerHTML
* id, className
* classList &gt;&gt; MDN
* Attribute - has, get, set, remove
* createElement, createTextNode, appendChild, append \(ex. figure and figcaption\)

### Inline CSS

* style, cssText
* camelCase
* e doar un atribut



