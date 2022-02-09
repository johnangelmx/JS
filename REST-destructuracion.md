# REST

La sintaxis de los parámetros rest (...) nos permiten representar un número indefinido de argumentos como un array.  
Cabe recalcar que el parametro REST se coloca antes del parametro a utilizar dentro de la funcion

```
(...nombreParametro)
```
## Consideraciones al usar el parametro REST
> Despues del parametro rest, no puede venir otro argumento  

> Si se necesita extraer una variable antes del rest, el primer valor tendra su propio argumento independiente

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

> Arguments(5) [10, true, false, 'Angel', 'Hola', callee: ƒ, Symbol(Symbol.iterator): ƒ]

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

En pocas palabras la sintaxis rest, permite crear un arreglo a datos que estos se encuentren almacenando mas variables

# Retornando de manera ordena (Arreglos)
dado el ejemplo anterior , la facilidad que se tiene al enviar y recibir argumento por medio del parametro REST a demostrado la facilidad de recibir un arreglo, pero como se puede mejorar la forma en la cual lo reutilizamos, es decir si en lugar, de necesitar el arreglo necesitaramos declarar las variable separadas?  
Para ello utilizamos la funcion de flecha junto la declaracion de cada una de las mismas:    
     
Definimos la funcion:
```
const imprimeArgumentos = (...args) => {
  return args;
};
```
la declaramos:  
```
imprimeArgumentos(10, true, false, "Fernado", "Hola");
```
Pero esa declaracion la guardamos en una variable para que retorne los argumentos, enviados
```
const argumentos = imprimeArgumentos(10, true, false, "Fernado", "Hola");
```
Ahora bien, el resultado de imprimir la variable argumentos seria un arreglo con todos los argumentos enviados, pero si queremos declarar cada valor dentro del arreglo en variable , es decir que suponiendo que el **10** dentro de los argumentos en la edad , vendria siendo la declaracion de la siguiente manera:   
`const edad = argumentos[0];`  
Y asi consecutivamente, para poder agilizar esta cuestion , se puede declarar de la misma forma en que se retorna las variable a declarar , es decir en lugar de ingresar una unica varible , **En este caso "argumentos"** se declara el arreglo de nombre que adquidiran las variable, ejemplo:  
```
const [casado, vivo, nombre,saludo] = imprimeArgumentos(10, true, false, "Fernado", "Hola");
```
Como resultado: 
> {casado: true, vivo: false, nombre: 'Fernado', saludo: 'Hola'}
  
Cada una con su repectiva declaracion de variable.

# Retornando de manera ordena (Objetos)
Tomando el ejemplo anterior, cabe mencionar que de la misma manera se puede declarar variable por varible en la misma declaracion pero en este caso , seria con { } llaves.  
En este caso, para ejemplificarlo declaramos la funcion: 
```
const crearPersona = (nombre, apellido) => ({ nombre, apellido });
```
La declaramos: 
```
crearPersona("Fernando", "Herrera");
```
Pero esa declaracion la guardamos en una variable:
```
const persona = crearPersona("Fernando", "Herrera");
```
El resultado de imprimir la variable **persona** , es la de un objeto que tiene las propiedades nombre y apellido, en caso de declarar una unica propiedad y esta convertirla en variable, seria de la siguiente manera:   
Vamos a declarar unicamente apellido
```
const {apellido} = crearPersona("Fernando", "Herrera");
```
Teniendo como resultado, una constante con el nombre de la variable siendo apellido y el valor siendo "herrera"  
Pero que pasaria si quisiera cambiar de nombre variable, entonces de declararia:  
```
const {apellido: nuevoApellido} = crearPersona("Fernando", "Herrera");
```
Tomando a **nuevoApellido** como el nuevo nombre de variable.