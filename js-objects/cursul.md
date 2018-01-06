```js
if(condition) {

}

if(condition) {

} else {

}

switch(condition) {
    case 1:
        // condition === 1
        break
    case 2:
        // condition === 2
        break
    default:
        // else
}


while(i < 10) {
    // bucla
}

for(let i = 0; i < array.length; i++) {
    let value = array[i]
}

i = 0
do {
    // bucla
    i++
} while(i > 0)

for (let key in obj) {
    // bucla prin key sau indecsi
}

for (let value of array) {
    // bucla prin valori
}


const obj = {
    a: 'q',
    b: 'w',
    c: 'e'
}

for (let key of Object.keys(obj)) {
    console.log('key:', key)
}
for (let value of Object.values(obj)) {
    console.log('value:', value)
}
for (let [key, value] of Object.entries(obj)) {
    console.log('key:', key, 'value:', value)
}




// try catch block
try {
  document.querySelector('asfsa').addEventListener('click', () => {})
} catch(eroare) {
    console.log(eroare)
} finally {
    const a = 1 + 2
  console.log(a)
}



const url = 'https://swapi.co/api/films/1/'

const firstMovie = new Promise((resolve, reject) => {
    const xhr = new XMLHttpRequest();
    xhr.open("GET", url);
    xhr.onload = () => resolve(xhr.responseText);
    xhr.onerror = () => reject(xhr.statusText);
    xhr.send();
});

function echoMovie(response) {
    const obj = JSON.parse(response)
    console.log(obj)
}

firstMovie
    .then(echoMovie)
    .catch(error => console.error(error))


```



