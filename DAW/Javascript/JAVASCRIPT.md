Javascript puro: Vanilla javascript
Framework: React
Babel: Capa intermedia que hace que nuestro código JS sea valido en todos los navegadores

NVM: gestos de versiones de NPM (JS)

ejemplo de arrays destructuring:

```js
const arr= [1,2,3,4,5,[6,7,8,9,10]];

console.log(arr)

console.log(arr[1])

console.log(arr[arr.length-1])

  
const [primero,segundo,tercero, ,quinto,sexto,septimo="no existe"] = arr;

console.log(primero,segundo,tercero,quinto, sexto)

console.log(septimo)

const menu = ['judias verdes' ,'lentejas', 'natillas'];
//Forma tradicional
const aux = menu[1]

menu[1] = menu[0]

menu[0] = aux

console.log(menu)


const menu = ["judias verdes", "lentejas", "natillas"];

let [primerPlato, segundoPlato, postre] = menu;

console.log(primerPlato);

console.log(segundoPlato);

console.log(postre);

([menu[0], menu[1]] = [menu[1],menu[0]]);

console.log(menu);
menu.push('pescado')

console.log(menu)
```


```js
//object destructuring
const persona = {

nombre: 'Juan',

apellido: 'Perez',

edad: 25,

profesion: 'desarrollador web',

ciudad: 'Barcelona',

nombreCompleto: function(){

return `${this.nombre} ${this.apellido}`

}

}

const {profesion:job, edad:age} = persona
console.log(job)

console.log(persona.nombre)

  
const {nombre,edad} = persona

console.log(nombre);

console.log(persona.nombreCompleto());

```

Ejemplo restaurante

```js
const restaurant = {

name: "Classico Italiano",

location: "Via Angelo Tava e nti 23, Firenze, Italy",

categories: ["Italian", "Pizzeria", "Vegetarian", "Organic"],

starterMenu: ["Focaccia", "Bruschetta", "Garlic Bread", "Caprese Salad"],

mainMenu: ["Pizza", "Pasta", "Risotto"],

openingHours: {

thu: {

open: 12,

close: 22,

},

fri: {

open: 11,

close: 23,

},

sat: {

open: 0, // Open 24 hours

close: 24,

},

},

order: function (starterIndex, mainIndex) {

return [this.starterMenu[starterIndex], this.mainMenu[mainIndex]];

},

};

  

const {name:restaurantName} = restaurant

console.log(restaurantName)

const {openingHours: {fri:horarioViernes} } = restaurant

console.log(horarioViernes)
```
