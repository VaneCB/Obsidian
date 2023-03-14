[[Arrays parte 2]]
```js
//basicos: map, filter y reduce
//para recorrer sin mas utilizas foreach para recorrer y hacer cambios usas el map

//CON MAP. siempre se recoge todo el array y se devuelve con los cambios realizados
const numeros = [1,2,3,4,5,6,7,8,9,10]
const numerosExplicados = numeros.map(numero=>numero%2===0 ? `${numero}--par`: `${numero}--impar`)
console.log(numerosExplicados)

//otro ejemplo
const numerosDobles = numeros.map(numero => numero*2)
console.log(numerosDobles)

//FILTER. NO modifica, nos filtra en base al parametro establecido

const numeros2 = [1,-2,3,-4,5,-6,7,-8,9,-10]

const numerosPositivos = numeros2.filter(numero=> numero>0)
console.log(numerosPositivos)

//Dado numero 2, sumar 3 a cada elemento, quitar negativos y calcular el triple de cada elemento resultante
const numerosSumados = numeros2.map(numero =>numero+3)
const numerosFiltrados = numerosSumados.filter(numero => numero>0)
const numerosTriple = numerosFiltrados.map (numero=> numero*3)
console.log(numerosTriple)

  
//forma mas rapida, concatenando
const resultado = numeros2
						 .map(numero=>numero+3)

						 .filter(numero=>numero>0)

						 .map(numero=> numero*3)

console.log(resultado)

//REDUCE
const numerosPares = [2,4,6,8,10]
//acc acumulado, cur current, i el indice, arr el array total
const suma = numerosPares.reduce((acc,cur)=>cur+acc,0)
console.log(suma)


const numeros3 = [1,4,6,8,10,15,17]
//suma de los elementos de numeros3 si son pares
const sumado = numeros3.filter(numero=>numero%2===0)
					   .reduce((acc,cur)=>acc+cur,0)

console.log(sumado)

//mismo caso pero solo con reduce
const sumaNumeros = numeros3.reduce((acc, cur,i, arr)=>{
if(cur%2===0) {
return cur+acc
}else{
return acc
}
},0)
console.log(sumaNumeros)

//Solo con reduce y un ternario
const sumaNumeros2 = numeros3.reduce((acc, cur,) => cur%2===0 ? cur+acc : acc, 0);
console.log(sumaNumeros2)


//calcular el numero de elementos del array cuyo valor sea al menos igual a la posicion que ocupa en el array
const numeros = [1,0,3,2,4,8,3,2,1,10,7]

const numElementos = numeros.reduce((acc,cur,i,arr)=> {
if(i<=cur) return ++acc
else return acc
},0)
console.log(numElementos)

//Lo mismo con un ternario
const numElementos2 = numeros.reduce((acc,cur,i,arr)=> (i<= cur) ? ++acc : acc, 0)
console.log(numElementos2)

//Con reduce

const texto = "test";
//funcion calcular0ocurrenciaLetras: {t: 2, e: 1, s:1}
const texto2 = "supercalifragilisticoespialidoso";
console.log([...texto2])
const initValue = {}
const resultado = [...texto2].reduce((acc,cur,i,arr)=> {
if (acc[cur]) {acc[cur]= acc[cur]+1}
else acc[cur] = 1
return acc
}, initValue)

console.log(resultado)

//Lo mismo pero con ternario
const resultado2 = [...texto2].reduce((acc,cur)=> { acc[cur] = acc[cur] ? acc[cur]+1 : 1

return acc
},initValue)
console.log(resultado2)

//Con destructuracion
const resultado2 = [...texto2].reduce((acc,cur)=> acc[cur] = acc[cur] ? {...acc,[cur]: acc[cur]+1} : {...acc,[cur]:1}

,initValue)

console.log(resultado2)
```

