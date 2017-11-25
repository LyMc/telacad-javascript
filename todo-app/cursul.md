# Cursul

###### index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>ToDo App</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
</head>
<body>
    <div class="container">
        <header class="site-header">
            <h1 class="site-title">Todo App</h1>
        </header>
        <main id="app" class="app">
            <section class="add-item">
                <input type="text" class="add-item-field" autofocus>
                <button class="add-item-button">Add</button>
            </section>
            <div class="no-items hidden">No items</div>
            <ul class="items">
                <li class="item">
                    <label>
                        <input class="item-check" type="checkbox" autocomplete="false">
                        <span class="item-label">First item</span>
                    </label>
                    <button class="item-remove" data-listener="false">x</button>
                </li>
                <li class="item">
                    <label>
                        <input class="item-check" type="checkbox" autocomplete="false">
                        <span class="item-label">Second item</span>
                    </label>
                    <button class="item-remove">x</button>
                </li>
            </ul>
            <section class="filters">
                <button class="current" id="filter-all" data-filter="all">All</button>
                <button id="filter-active" data-filter="active">Active</button>
                <button id="filter-completed" data-filter="completed">Completed</button>
            </section>
        </main>
        <footer class="site-footer">
            <p class="copy">Made @ TelAcad</p>
        </footer>
    </div>
</body>
</html>
```

###### style.css

```css
/* Reset */
*,
*::before,
*::after {
    box-sizing: border-box;
}
body {
    margin: 0;
}

/* Main */
body {
    background-color: #ddd;
}
.container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
}
.site-header {
    text-align: center;
    padding-bottom: 50px;
}
.site-title {
    margin: 0;
}
.site-footer {
    text-align: center;
    color: #999;
    padding: 15px;
}
.site-footer p {
    margin: 0;
}
.app {
    min-height: calc(100vh - 87px - 48px);
}

/* App */
.add-item {
    display: flex;
}
.add-item-field {
    width: 100%;
    border: none;
    height: 48px;
    font-size: 36px;
    padding: 0 15px;
}
.add-item-button {
    border: none;
    background-color: #009688;
    color: #fff;
    font-size: 36px;
    text-transform: uppercase;
}
.items {
    font-size: 24px;
    list-style-type: none;
    padding: 0;
    margin: 50px 0;
}
.item.inactive {
    display: none;
}
.item-check:checked + .item-label {
    text-decoration: line-through;
}
.item-remove {
    border-radius: 100%;
    color: #fff;
    background-color: #f00;
    border: none;
    width: 20px;
    height: 20px;
    font-size: 20px;
    line-height: 15px;
    text-align: center;
}
.no-items.hidden {
    display: none;
}

.filters button.current {
    color: #fff;
    background-color: #009688;
}
```

###### script.js

```js
/* eslint-disable */
(function(){
    // aici scrim cod
})()
function main() {
    const fieldElement = document.querySelector('#app .add-item-field')
    const addButtonElement = document.querySelector('#app .add-item-button')
    const itemsElement = document.querySelector('#app .items')
    const noItemsElement = document.querySelector('#app .no-items')
    const filtersElement = document.querySelector('#app .filters')
    const filters = {
        all: filtersElement.querySelector('#filter-all'),
        active: filtersElement.querySelector('#filter-active'),
        completed: filtersElement.querySelector('#filter-completed')
    }
    // creez o referinta catre item
    let itemElements
    let countItems = 0
    let currentFilter = 'all'
    // creez o functie care va actualiza referinta
    function updateItemElements() {
        itemElements = itemsElement.querySelectorAll('.item')
        
        countItems = itemElements.length
        if (countItems === 0) {
            noItemsElement.classList.remove('hidden')
        } else {
            noItemsElement.classList.add('hidden')
            for (let i = 0; i < countItems; i++) {
                const removeElement = itemElements[i].querySelector('.item-remove')
                const checkElement = itemElements[i].querySelector('.item-check')
                console.log(currentFilter, checkElement.checked)
                if (currentFilter === 'all') {
                    itemElements[i].classList.remove('inactive')
                } else {
                    if (currentFilter === 'active') {
                        if (!checkElement.checked) {
                            itemElements[i].classList.remove('inactive')
                        } else {
                            itemElements[i].classList.add('inactive')
                        }
                    } else {
                        if (checkElement.checked) {
                            itemElements[i].classList.remove('inactive')
                        } else {
                            itemElements[i].classList.add('inactive')
                        }
                    }
                }
                if (removeElement.dataset.listener !== 'true') {
                    removeElement.dataset.listener = 'true'
                    function remove() {
                        itemsElement.removeChild(this.parentElement)
                        updateItemElements()
                    }
                    removeElement.addEventListener('click', remove)
                }
            }
        }
    }
    // apelez prima oara pentru a avea primele elemente
    updateItemElements()
    
    // functia de adaugare a unui item nou
    function addNewItem() {
        // salvez valoarea input-ului intr-o variabila
        const fieldValue = fieldElement.value
        // creez un nou element, in care adaug valoarea de mai sus si clasa .item
        const newItemElement = document.createElement('li')
        // template string din ES6
        newItemElement.innerHTML = `
            <label>
                <input class="item-check" type="checkbox" autocomplete="false">
                <span class="item-label">${ fieldValue }</span>
            </label>
            <button class="item-remove">x</button>`
        // aceeasi chestie facuta fara ES6
//        newItemElement.innerHTML = 
//            '<label>' +
//                '<input class="item-check" type="checkbox" autocomplete="false">' +
//                '<span class="item-label">' + fieldValue + '</span>' +
//            '</label>'
        newItemElement.classList.add('item')
        // atasez elementul creat listei cu items
        itemsElement.appendChild(newItemElement)
        // actualizez referintele catre lista cu itemi
        updateItemElements()
        // sterg valoarea din input
        fieldElement.value = ''
        // revin cu focusul pe input
        fieldElement.focus()
        
        console.log(itemElements)
    }
    // Atasez un listener pe butonul nostru
    addButtonElement.addEventListener('click', addNewItem)
    fieldElement.addEventListener('keypress', function(event) {
        if (event.keyCode === 13) {
            addNewItem()
        }
    })
    
    function changeFilter() {
        // setez filtrul in variabila potrivita
        currentFilter = this.dataset.filter
        updateItemElements()
        // afisez cine e activ acum
        filters.all.classList.remove('current')
        filters.active.classList.remove('current')
        filters.completed.classList.remove('current')
        this.classList.add('current')
    }
    filters.all.addEventListener('click', changeFilter)
    filters.active.addEventListener('click', changeFilter)
    filters.completed.addEventListener('click', changeFilter)
}

window.addEventListener('load', main)

```



