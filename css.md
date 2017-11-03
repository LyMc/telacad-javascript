# Cursul 2 - CSS

Un curs detaliat despre CSS.

### index.htm

```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title>GETTING STARTED WITH BRACKETS</title>
        <meta name="description" content="An interactive getting started guide for Brackets.">
        <link rel="stylesheet"  href="main.css">
    </head>
    <body>      
       <h2 class="contact-email" title="Scrie-mi" contenteditable>victor@locoman.ro</h2>

       <p><input type="text" name="Nume" placeholder="Nume"></p>
       <p><input type="email" name="Nume" placeholder="Parola"></p>

       <h2 class="titlu" id="titlu-css">CSS</h2>
       <section>
           <h3 class="sub-titlu">Cascading</h3>
           <h3 class="sub-titlu">Style</h3>
           <h3 class="sub-titlu">Sheets</h3>
       </section>

       <h2 class="titlu">CSS <em>Levels</em></h2>

       <h3>Lv 1</h3>
       <h3>Lv 2</h3>
       <h3>Lv 3</h3>

       <em>Levels</em>

       <h2>Selectori</h2>

       <p>
            tag {
                proprietate: valoare;
            }
            .clasa-mea {}
            #id-ul-meu {}
       </p>

       <section>
           <h2>Box Model</h2>
           <img src="images/download.jpg" alt="Lorem Ipsum" class="imaginea-mea">
       </section>

       <section>
           <h2>Border Box vs Content Box</h2>
           <div class="box">
               <div class="item empty">Spatiu</div>
               <div class="item image"><img src="http://lorempixel.com/200/200/" alt="Lorem Ipsum" class="img"></div>
               <div class="item text">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Non tempora rerum autem dolores esse nihil delectus error itaque aspernatur, architecto aliquid iusto, in fugiat amet! Quisquam doloribus, consectetur perspiciatis. Consectetur!</div>
               <div class="item empty">Spatiu</div>
               <div class="clear"></div>
           </div>
       </section>

       <section>
           <h2>Tema</h2>
           <ul>
               <li>O pagina de html care sa aiba un header, un main, un aside si un footer</li>
               <li>in header: menu (nav, lista), logo, titlu</li>
               <li>in main: articol, titlu, continut, imagini</li>
               <li>sidebar: categorie cu alte articole</li>
               <li>footer: despre autor, newsletter(nume, email, submit)</li>
               <li>folositi Flexbox</li>
               <li>centrati continutul intr-un container</li>
               <li>nu folositi fisiere externe (doar css)</li>
           </ul>
       </section>

    </body>
</html>
```

### main.css

```css
/* puțină stilizare de la brackets, o vom păstra */
html {
    background: #e6e9e9;
}
body {
    background: #fff;
    box-shadow: 0 0 2px rgba(0, 0, 0, 0.06);
    color: #545454;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-size: 16px;
    line-height: 1.5;
    margin: 0 auto;
    max-width: 800px;
    padding: 2em 2em 4em;
}
h1, h2, h3, h4, h5, h6 {
    color: #222;
    font-weight: 600;
    line-height: 1.3;
}
a {
    color: #0083e8;
}
b, strong {
    font-weight: 600;
}

/* de aici venim cu modificările noastre */
.contact-email:hover {
    color: blueviolet;
}
.contact-email:focus {
    text-decoration: line-through;
}
.contact-email[title="Scrie-mi"] {
    font-size: 30px;
}
input[type="email"] {
    background-color: coral;
}
h2 {
    margin-bottom: 1px;
}
h2 + h3 {
    border-top: 1px solid;
    margin-top: 1px;
    padding-top: 15px;
}
h2, h3, h4 {
    text-align: right;
}

h3::before {
    content: "+ ";
}
h3::after {
    content: "$";
    color: blue;
}
h3:nth-child(2n + 1) {
    color: green;
}
h3:nth-last-child(1) {
    color: darkgoldenrod;
}

.titlu {
}

#titlu-css {
}
.imaginea-mea {
    padding: 15px;
}

.imaginea-mea {
    padding-bottom: 50px;
    border-width: 1px;
    border-radius: 50px;
    margin: 15px;
    background-color: cadetblue;
}

/* Box model: border box vs content box */
.box {
    background-color: beige;
    width: 800px;
    /*overflow: hidden; fixeaza problema cu float */
    position: relative;
}
.item {
    width: 25%;
    height: 200px;
    /*float: left;*/
}
.clear {
    clear: both;
}
.item.empty {
    background-color: #0c5;
    text-align: center;
    line-height: 200px;
    color: #fff;
}
.item.image {
    /*position: absolute;*/
    top: 100px;
    left: 100px;
    /*z-index: 10;*/
}
.item.image .img {
    width: 100%;
    height: 100%;
    border: none;
    margin: 0;
    border-radius: 0;
}
.item.text {
    padding: 10px;
    border: 1px solid;
    /*width: calc(25% - 22px);*/
    position: relative;
}

*,
*::before,
*::after {
    box-sizing: border-box;
}

.box {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 400px;
/*
    position: absolute;
    left: 0;
    bottom: 0;
    right: 0;
    top: 0;
    margin: auto;
    width: 200px;
*/
}

.item {
    width: 100px;
}
.item.text {
    order: 1
}
.item.image {
    order: 2;
}
```

Resurse utile:

* [MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS)
* [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [un mod distractiv de a învăța flexbox](http://flexboxfroggy.com/)
* [alt mod pentru fanii tower defense](http://www.flexboxdefense.com/)

[Formularul de feedback](https://victorlocoman.typeform.com/to/ClOi6C)

