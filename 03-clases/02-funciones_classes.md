# Funciones que funcionan como clases

Para plantear una idea de como sirven las clases tomemos el ejemplo anterior y hablemos del problema

```
const fher = {
  nombre: 'Fernado',
  edad: 30,
  imprimir () {
    console.log(`Nombre: ${this.nombre} - Edad: ${this.edad}`)
  }
}

fher.imprimir();
```

ya como hemos visto la forma en la cual podemos utlizar dicho **objeto** es en singular ,unicamente podemos definirlo e imprimirlo con la palabra reservada `this` , claro!, podremos hacer una funcion que imprima los resultados de enviarle el objeto y reutilizarlos en la misma , pero esto no es estandar y ya no es muy utilizado, incluso JavaScript tomando de una forma arcaica lo de utilizarlo en un una funcion hace mucho tiempo se hacia lo mismo para crear un generador de objetos.

En pocas palabras JS en su tiempo utilizo las funciones para crear objetos.  
Y las clases como pequeña introduccion es eso, un generador de objetos como tal.

Ejemplo de "**clases**" con funciones

```
function Persona (nombre, edad) {
  console.log(`Se ejecuto esta linea`)
}

Persona()
```

como se puede visualizar se ve como una funcion normal , y se ejecuta como una misma , sin embargo aqui lo que queremos visualizar la forma en la cual generamos un objeto e imprimimos un resultado.  
El ejemplo anterior imprime `>Se ejecuto esta linea`.  
Teniendo en cuenta que la funcion/clase contiene en sus parametros nombre y edad , en una funcion/clase , se plantea que esos son las propiedades a adquidir , para ello le enviaremos los parametros:

```
function Persona (nombre, edad) {
  console.log(`Se ejecuto esta linea`)
  this.nombre = nombre
  this.edad = edad
}
```

Al asignarle el this en esta funcion/clase le estamos diciendo al codigo, que quiero que seas un generador de objetos, que los parametros que recibas tendran las propiedades de nombre y de edad ,efectuando el nombre y edad como `this.nombre` y `this.edad` (estos podriamos cambiarlos por los nombres de las propiedades que nosotros desearamos), y como hacemos para almacenar este **"NUEVO"** objeto?

```
const maria = new Persona('Maria', 18)
```

Para poder ejecutar este generador de objetos, utilizamos la palabra reservada new para hacer una nueva instancia de nuestas funcion/clase y asi obtenido el siguiente resultado al imprimirlo:  
`Persona {nombre: 'Maria', edad: 18`  
Ahora bien podremos hacer multiples objetos, con las propiedades nombre y edad:

```
const melissa = new Persona('Melissa', 35)
```

`Persona {nombre: 'Melissa', edad: 35`

```
const fher = new Persona('Fernando', 30)
```

`Persona {nombre: 'Fernando', edad: 30`

Pero aun nos falta resolver un problema tomando en cuenta el primer ejemplo de esta pagina...Como podremos ingresar una funcion en un generador de objetos(funcion/clase)?  
Para ello de la misma forma que utilizamos el `this.parametro =` podremos ingresar una funcion de la siguiente manera:

```
this.imprimir = () => {
    console.log(`Nombre: ${this.nombre} - Edad: ${this.edad}`)
  }
```

Asi es como quedaria nuestra funcion a ingresar al codigo de Persona(funcion/clase)
, ingresemoslo e imprimamosla:

```
function Persona (nombre, edad) {
  console.log(`Se ejecuto esta linea`)
  this.nombre = nombre
  this.edad = edad
  this.imprimir = () => {
    console.log(`Nombre: ${this.nombre} - Edad: ${this.edad}`)
  }
}
```

y para imprimirla o mejor dicho aceder a la funcion que imprime utilizamos el nombre de la variable a la que almacenamos el objeto dicho creado y como si estuvieramos accediendo a un objeto comun llamamos a imprimir:

```
const melissa = new Persona('Melissa', 35)
melissa.imprimir()
```

Teniendo como resultado:
`>Nombre: Melissa - Edad: 35`

Asi demostrando la forma antes del EMAC6 como se generaban las clases en JS