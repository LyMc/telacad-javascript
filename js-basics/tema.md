# Tema JS Basics

O pagina a unui magazin online cu cateva produse.
+ Header - numele magazinului, imagine, menu (nav)
+ Main - o lista de produse
+ article - nume, pret, poza (bonus / provocare: folositi imagini de marimi diferite, centrate pe un dreptunghi), buton de adauga in cos
+ aside - lista de categorii
+ footer - abonare newsletter, despre magazin
+ responsive (`ctrl + shift + m`)

```html
<main class="container">
 <article class="left"></article>
 <aside class="right"></aside>
</main>
```
```css
.container {
 display: flex;
}
.left {
 order: 1;
}
.right {
 order: 2;
}
@media (max-width: 600px) {
 h1 {
  width: 100%;
 }
 p {
  font-size: 16px;
 }
 .left {
  order: 2;
 }
 .right {
  order: 1;
 }
}
```
+ flexbox


Urcati tema aici!

Nu uitati de feedback :)