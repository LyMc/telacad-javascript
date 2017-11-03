# Cursul 2 - CSS

Un curs detaliat despre CSS.

```js
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

Resurse utile:

* [MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS)
* [Flexbox Guide](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)
* [un mod distractiv de a învăța flexbox](http://flexboxfroggy.com/)
* [alt mod pentru fanii tower defense](http://www.flexboxdefense.com/)

[Formularul de feedback](https://victorlocoman.typeform.com/to/ClOi6C)

