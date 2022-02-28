# Planteando el problema 
Actualmente la programacion orientada objetos dicta la forma en la cual podemos utilizar un fragmento de codigo y generarle un tipo de identidad, a lo cual sabemos hacerlo en este punto.
Sin embargo es facil decir que no hay un problema con esto , que pues si lo hay!.  
Para poder plantear de mejor manero lo anterior dicho , veamoslo en el ejemplo:
```
const fher = {
  nombre: 'Fernado',
  edad: 30,
}

const pedro = {
  nombre: 'Pedro',
  edad: 15,
}
```
Tomando en cuenta la observacion anterior de los objetos , porder ver y definirlos como lo anterior visto , sin embargo , que pasaria si se tiene que imprimir estos dos o mas objetos en un futuro, o reutilizarlo incluso invocarlos de cierta forma?.  
Para ello tomaremos la opcion de imprimirlos:
``` 
const fher = {
  nombre: 'Fernado',
  edad: 30,
  imprimir () {
    console.log(`Nombre: ${nombre} - Edad: ${edad}`)
  }
}

fher.imprimir();
```
Suponiendo que el codigo se ejecute tendremos un error, dado que las variable no estan declaradas hasta ese punto de la ejecucion y son inaccesibles al mismo objeto.  
Para ello , existe el `this` 
# this
La palabra reservadad `this` en pocas palabras podriamos definirla en:   
El objeto contexto de JavaScript en el cual se está ejecutando el código actual.

  
Esto nos ayudara a poder imprimir las propiedades en el propio objeto anterior, de la siguiente manera:
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
Y como resultado:
```
Nombre: Fernando - Edad: 30
```
Demostrando asi la utilidad de esta palabra reservasda