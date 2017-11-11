Cod

```html
<!doctype html>
<html>
<head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
    <title>Let's code</title>
    <link href="style.css" type="text/css" rel="stylesheet">
    <script src="script.js"></script>
</head>
<body>
    <div class="container">
        <header class="site-header">
            <h1 class="site-title">Let's code</h1>
            <nav class="site-menu">
                <ul>
                    <li><a href="">Home</a></li>
                    <li><a href="">Magazin</a></li>
                    <li><a href="">Contact</a></li>
                </ul>
            </nav>
        </header>
        <div class="main-container">
            <main class="products">
                <h2 class="products-title">Produse</h2>
                <article class="product">
                    <h3 class="product-title">Un script smecher</h3>
                    <div class="image-container">
                        <img class="product-image" src="http://lorempixel.com/1000/500/technics/2" alt="Imaginea produsului">
                    </div>
                    <p class="product-description">Acest script e atat de smecher incat stie sa zica cat e ora</p>
                    <div class="price-container">
                        <div class="product-price">Pret: <strong>99.99</strong> Euro</div>
                        <button class="add-to-cart">Il vreau</button>
                    </div>
                </article>
                <article class="product">
                    <h3 class="product-title">Un script smecher</h3>
                    <div class="image-container">
                        <img class="product-image" src="http://lorempixel.com/100/50/technics/4" alt="Imaginea produsului">
                    </div>
                    <p class="product-description">Acest script e atat de smecher incat stie sa zica cat e ora</p>
                    <div class="price-container">
                        <div class="product-price">Pret: <strong>99.99</strong> Euro</div>
                        <button class="add-to-cart">Il vreau</button>
                    </div>
                </article>
                <article class="product">
                    <h3 class="product-title">Un script smecher</h3>
                    <div class="image-container">
                        <img class="product-image" src="http://lorempixel.com/100/50/technics/6" alt="Imaginea produsului">
                    </div>
                    <p class="product-description">Acest script e atat de smecher incat stie sa zica cat e ora</p>
                    <div class="price-container">
                        <div class="product-price">Pret: <strong>99.99</strong> Euro</div>
                        <button class="add-to-cart">Il vreau</button>
                    </div>
                </article>
                <article class="product">
                    <h3 class="product-title">Un script smecher</h3>
                    <div class="image-container">
                        <img class="product-image" src="http://lorempixel.com/100/50/technics/9" alt="Imaginea produsului">
                    </div>
                    <p class="product-description">Acest script e atat de smecher incat stie sa zica cat e ora</p>
                    <div class="price-container">
                        <div class="product-price">Pret: <strong>99.99</strong> Euro</div>
                        <button class="add-to-cart">Il vreau</button>
                    </div>
                </article>
            </main>
            <aside class="categories">
                <h2 class="categories-title">Categorii</h2>
                <ul>
                    <li><a class="category" href="">Cod general</a></li>
                    <li><a class="category" href="">Hacks</a></li>
                    <li><a class="category" href="">Tricks</a></li>
                </ul>
            </aside>
        </div>
    </div>
    <div class="footer-container">
        <footer class="container site-footer">
            <section class="about-us">
                <h3>Despre noi</h3>
                <p>Scrie cod &gt; vinde cod &gt; profit</p>
            </section>
            <section class="newsletter">
                <h3>Newsletter</h3>
                <form action="subscribe.html" method="post">
                    <input type="email">
                    <button type="submit">Aboneaza-ma</button>
                </form>
            </section>
        </footer>
    </div>
</body>
</html>
```

style.css

```css
/* Reset */
body {
    margin: 0;
}
*,
*::before,
*::after {
    box-sizing: border-box;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    padding: 0 15px;
}

/* Site header */
.site-header {
    background: url("https://www.softwarecornwall.org/wp-content/uploads/2015/07/code.jpg") no-repeat center / cover;
    color: #00bcd4;
    display: flex;
    justify-content: space-between;
    align-items: center;
    transition: background .4s ease;
    flex-wrap: wrap;
}
.site-header:hover {
    background-image: url("http://lorempixel.com/400/200/technics");
}
.site-title {
    padding: 15px;
    margin: 0;
    text-shadow: 2px 2px 5px #000;
}
.site-menu ul {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
}
.site-menu a {
    color: inherit;
    text-decoration: none;
    margin: 0 10px;
}
.site-menu a:hover {
    text-decoration: underline;
}

/* Products */
.main-container {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    min-height: calc(100vh - 157px);
}
@media (max-width: 600px) {
    .main-container {
        flex-wrap: wrap;
    }
}
.products {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
}
@media (min-width: 601px) {
    .products {
        order: 2;
    }
    .categories {
        order: 1;
    }
}
.products-title {
    width: 100%;
}
.product {
    width: 100%;
/*    border: 1px solid #000;*/
    margin-bottom: 15px;
    background-color: #e0f7fa;
    padding: 10px;
}
@media (min-width: 361px) {
    .product {
        width: calc(50% - 7.5px);
    }
}
.product-title {
    text-align: center;
}
.image-container {
    height: 150px;
    display: flex;
    justify-content: center;
    align-items: center;
}
.product-image {
    max-width: 100%;
    max-height: 100%;
}
.product-description {
    color: #333;
}
.price-container {
    display: flex;
    justify-content: space-between
}
.product-price {
    font-size: 24px;
}
.product-price strong {
    font-size: 28px;
}
.add-to-cart {
    background: #00bcd4;
    border: none;
    color: #fff;
    text-transform: uppercase;
}
.add-to-cart:hover {
    background: #fff;
    color: #00bcd4;
} 

/* Categories */
.categories {
    min-width: 150px;
}
.categories-title {
    text-align: center;
}
.category {
    color: #000;
    text-decoration: none;
}
.category:hover {
    text-decoration: underline;
}

/* footer */
.footer-container {
    background-color: #cfd8dc;
}
.site-footer {
    display: flex;
    justify-content: space-between;
}
```

script.js

```js
/* eslint-disable */
function myApp() {
//    var button = document.querySelector('.add-to-cart')
    var button = document.querySelectorAll('.add-to-cart')
    for (var i = 0; i < button.length; i++) {
        button[i].addEventListener('click', function() {
            this.style.color = 'red'
        })
    }
}

window.addEventListener('load', myApp)

```



