# REST
La sintaxis de los parámetros rest (...) nos permiten representar un número indefinido de argumentos como un array.  

Ejemplo:  
Teniendo en cuenta que la palabra reservada **arguments** en una funcion, demuestra los parametros que invocas en una funcion: 
```
function imprimeArgumentos () {
    console.log(arguments);
}
```
Invocandolo:  
```
console.log(imprimeArgumentos(10,true,false,'Angel', 'Hola'))
```
Resultado:
>Arguments(5) [10, true, false, 'Angel', 'Hola', callee: ƒ, Symbol(Symbol.iterator): ƒ]

Teniendo en cuenta el primer ejemplo, con una funcion de flecha seria:
```
const imprimeArgumentos2 = (args) => args;
```
Para poder imprimir argumentos en una funcion de flecha se tiene que invocar **arguments** o su acronimo **args** en parametros para poder visualizar dichos argumentos,pero el resultado es:
> 10    

Dado que el resultado solo es un valor en este caso se tiende a utilizar la sintaxis **REST**, el cual nos permitira almacenar los argumentos dados en una arreglo, es decir :  
```
const imprimeArgumentos2 = (...args) => args;
```
Siendo el resultado:  
> (5) [10, true, false, 'Angel', 'Hola']

