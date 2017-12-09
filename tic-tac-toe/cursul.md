### index.htm

```html
<!doctype html>
<html lang="ro">
<head>
    <meta charset="utf-8">
    <title>Tic Tac Toe</title>
    <link href="style.css" type="text/css" rel="stylesheet">
    <script src="script.js"></script>
</head>
<body>
    <header>
        <h1 class="title">Tic Tac Toe</h1>
    </header>
    <main id="app">
        <div class="block">
            <div class="square">0</div>
            <div class="square">1</div>
            <div class="square">2</div>
            <div class="square">3</div>
            <div class="square">4</div>
            <div class="square">5</div>
            <div class="square">6</div>
            <div class="square">7</div>
            <div class="square">8</div>
        </div>
        <div class="gameStatus"></div>
        <button class="resetGame">Reset</button>
        
        <!--+ Structura jocului (html)
        + Stilizarea (css)
        + Selectarea elementelor de interactiune
        + Definirea interactiunilor cu utilizatorul (addEventListener)
        + Definirea si stocarea datelor (js >>)
        + Functia de actualizare date (calcule, logica jocului)
        + Functia de randare (afisare date)-->
    </main>
</body>
</html>
```



### style.css

```css
*,
*::before,
*::after {
    box-sizing: border-box;
}
body {
    margin: 0;
    background-color: #eee;
}

.title {
    text-align: center;
}
.block {
    display: grid;
    display: -ms-grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);
    grid-gap: 10px;
    width: 320px;
    height: 320px;
    margin: 0 auto;
}
.square {
    background-color: #7debab;
    font-size: 64px;
    line-height: 100px;
    text-align: center;
    text-transform: uppercase;
}
.square:hover {
    cursor: pointer;
}
.square.x {
    color: red;
}
.square.o {
    color: blue;
}

.gameStatus {
    text-align: center;
}
.gameStatus .winner {
    color: red;
    text-transform: uppercase;
}
.resetGame {
    margin: 15px auto;
    display: block;
}
```



### script.js

```js
/* eslint-disable */
function game() {
    const appElement = document.querySelector('#app')
    const blockElement = appElement.querySelector('.block')
    const squareElements = blockElement.querySelectorAll('.square')
    const gameStatusElement = appElement.querySelector('.gameStatus')
    const resetGameElement = appElement.querySelector('.resetGame')
    let state
    let winner
    const difficulty = 1
    
    /*for (let i = 0; i <= squareElements.length; i++) {
        let square = squareElements[i]
    }*/
    let i = 0
    for (let square of squareElements) {
        square.dataset.id = i++
    }
      
    function render(i) {
        const el = squareElements[i]
        el.innerHTML = state[i]
        if (state[i]) {
            el.classList.add(state[i])
        }
    }
    
    function whosNext() {
        let diff = 0
        for (let value of state) {
            if (value === 'x') {
                diff++
            }
            if (value === 'o') {
                diff--
            }
        }
        return diff > 0 ? 'o' : 'x'
        /*if (isX) {
            state[index] = 'x'
        } else {
            state[index] = 'o'
        }*/
    }
    
    function calc(index) {
        state[index] = whosNext()
    }
    
    function rotate() {
        state = [
            state[6],
            state[3],
            state[0],
            state[7],
            state[4],
            state[1],
            state[8],
            state[5],
            state[2]
        ]
    }
    
    function isAWinn(i, j, k) {
        const a = state[i]
        const b = state[j]
        const c = state[k]
        if (a && a === b && b === c) {
            return a
        }
        return false
    }
    
    function calcWinner() {
        for (let i = 0; i < 4; i++) {
            winner = isAWinn(0, 1, 2) || isAWinn(3, 4, 5) || isAWinn(0, 4, 8)
            if (winner) {
                return
            }
            rotate()
        }
    }
    
    function renderWinner() {
        if (winner) {
            gameStatusElement.innerHTML = 'The winner is <span class="winner">' + winner + '</span>'
        }
        if (state.indexOf('') === -1) {
            gameStatusElement.innerHTML = 'It\'s a draw'
        }
    }
    
    function handleClick(event) {
        // definim variabilele necesare
        const element = event.target
        const index = element.dataset.id
        // verificam daca suntem pe un element de X sau O
        if (!index) {
            return
        }
        // verificam daca avem deja un x sau o
        if (state[index]) {
            return
        }
        // verificam daca avem un castigator
        if (winner) {
            return
        }
        // verificam daca e egalitate
        if (state.indexOf('') === -1) {
            return
        }
        
        
        calc(index)
        render(index)
        calcWinner()
        renderWinner()
        
        if (!winner && state.indexOf('') > -1) {
            detectNextStep()
        }
    }
    
    function resetGame() {
        state = Array(9).fill('')
        winner = false
        for (let square of squareElements) {
            square.innerHTML = ''
            square.classList.remove('x')
            square.classList.remove('o')
        }
        gameStatusElement.innerHTML = ''
    }
    
    resetGame()
    
    blockElement.addEventListener('click', handleClick)
    resetGameElement.addEventListener('click', resetGame)
    
    // hai sa jucam cu PC-ul
    function detectNextStep() {
        let k = 0
        while (whosNext() === 'o') {
            let i
            if (difficulty === 1) {
                i = Math.floor(Math.random() * 9)
            } else if (difficulty === 2) {
                i = 0
            } else if (difficulty === 3) {
                i = 1
            }
            if (!state[i]) {
                calc(i)
                render(i)
                calcWinner()
                renderWinner()
            }
        }
    }
}

window.addEventListener('load', game)

```



