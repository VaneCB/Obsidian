[[Javascript array]]
```js
const letrasAbecedario = ['a','e','i','o','u']

//extraer un elemento del array
//slice es un metodo inmutable
console.log(letrasAbecedario.slice(2,5))

//SI le ponesmos el - cuenta desde el final
const letrasAbecedarioConSlide = letrasAbecedario.slice(-2)
console.log(letrasAbecedarioConSlide)

//copiar un array
const letrasAbecedarioClone = letrasAbecedario.slice()
letrasAbecedarioClone[0] = 'A'

//otra opcion de clone con sprite operator ...
const letrasAbecedarioClone2 = [...letrasAbecedario]

// metodos mutables (que cambian el array)
//splice quita elementos del array
letrasAbecedario.splice(2,3)
console.log(letrasAbecedario.splice(2,3))
console.log(letrasAbecedario)


const edadPerros = [2,5,8,9]
//tres formas de recorrer un array
//con un for (NO LO VAMOS A USAR)
for (let index = 0; index < edadPerros.length; index++) {

const element = edadPerros[index];

console.log(`Las edades de los perros son ${element} años`)
}

//ejemplo de cambio
for (let index = 0; index < edadPerros.length; index++) {
const element = edadPerros[index];
edadPerros[index] = `La edad del perro es${element} años`
console.log(edadPerros)
}

//con un forof (aunque se lea for, hemos puesto forof)
for (const edadPerro of edadPerros) {
console.log(`La edad del perro es${edadPerro} años`);
}

//con un foreach. NO permite break ni continue!!!
edadPerros.forEach(edadPerro => {
console.log(`La edad del perro es${edadPerro} años`);
});
```

[[Metodos de programacion funcional]]

