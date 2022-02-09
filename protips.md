# Retorno de funciones

Una forma mas eficiente de retornar un objeto es el siguiente, teniendo de ejemplo:

```
function crearPersona(nombre, apellido) {
  return {
    nombre: nombre,
    apellido: apellido,
  };
}
const persona = crearPersona("Fernando", "Herrera");

console.log(persona);
```

Teniendo como resultado:

> {nombre: 'Fernando', apellido: 'Herrera'}

Pero si al retornar un objeto, los nombres de las propiedades , son los mismos que los parametros de la funcion no necesita anotarlo dos veces, creando un codigo mas limpio:

```
function crearPersona(nombre, apellido) {
  return {nombre,apellido,};
}
```

# En funcion de flecha

Tomando el ejemplo anterior en funcion de flecha seria:

```
const crearPersona = (nombre, apellido) => ({ nombre, apellido });

const persona = crearPersona("Fernando", "Herrera");
console.log(persona);
```

Aqui cabe destacar que el tip que se utiliza es que cuando queremos retornar , sin la necesidad del return porner **{ }** no serviria dado que lo tomaria como el inicio de una funcion con return , para ello utilizamos las **( )** para poder utilizar el retorno de un objeto quedado:

```
 => ({ nombre, apellido })
```
los parentesis le dicen a javascript que es lo que quiere retornar  

# Destructuracion de argumentos
La destructuarion , permite elegir y manipular uno por uno , sin la necesidad de declarar y hacerlo uno por uno .Ejemplo  
Declaramos el siguiente objetos:
```
const tony = {
  nombre: "Tony Stark",
  codeName: "Ironman",
  vivo: false,
  edad: 40,
  trajes: ["Mark I", "Mark V", "Hulkbuster"],
};
```
declaramos una funcion de flecha: 
```
const imprimePropiedades = (personaje) => {
}; 
```
Para imprimir las propiedades del objeto anterior tendriamos que hacerlo uno por uno: 
```
const imprimePropiedades = (personaje) => {
  console.log('nombre: ', personaje.nombre);
  console.log('codeName: ', personaje.codeName);
  console.log('vivo: ', personaje.vivo);
  console.log('edad: ', personaje.edad);
  console.log('trajes: ', personaje.trajes);
};
``` 
Teniendo un codigo demasiado largo y mal visto , para ello utilizamos la destructuracion , para ello utilizamos las llaves **{ }** y declaramos dentro de los argumentos las propiedades a manipular dentro de la funcion.
```
const imprimePropiedades = ({nombre,codeName,vivo,edad,trajes}) => {
    console.log(nombre,codeName,vivo,edad,trajes)
};
```
Teniedo un codigo mas optimizado y mejor util.  
En dado caso que no recibamos de vuelta algun valor de una propiedad por ejemplo de la edad, se puede condicionar dentro de los parametros de la siguiente manera
```
const imprimePropiedades = ({nombre,codeName,vivo,edad = 15,trajes}) => {......
```
Asi ahora en adelante , si la propiedad no contiene un valor, se toma por defecto el valor de 15.
