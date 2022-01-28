# Guia Javascript

Hola mundo , y visualizacion en consola: <br>
`console.log('Hola mundo');` <br>
Hola mundo , y visualizacion en el navegador: <br>
`document.write('Hola mundo');` <br>
<br>
Nota: el primer comando por consola funciona de la misma manera en node.js

# Variable y comentarios

Comentarios: `// ` <br>
Variable, es un contenedor de informacion que apunta a un lugar en memoria. Dicha informacion puede cambiar en el futuro. <br>
Tipos de variables: <br>
`let ` La variable let es la mas recomendada hoy en dia dado que se ha convertido en un standar del lenguaje, es una variable que cambia conforme la utilizas. <br>
`var ` La variable var es la menos recomendada dado que que cierta forma esta variable puede cambiar palabras reservedas en alto nivel , es decir no tiene restriccion alguna antes al creacion y manipulacion de variable ya establecidas por el codigo o por el lenguaje <br>
`const` la variable const , sirve para declarar un valor que no puede ser modificado en un futuro , el valor es inmodificable <br>

# Tipo de console

`console.log( ) ` Es una forma estadar de ver la informacion en el navegador<br>
`console.warn( ) `La visualizacion estara en amarrillo con su respectivo icono de advertencia <br>
`console.error( ) `La visualizacion estara en rojo con su respectivo icono de Peligro o error<br>
`console.info( ) ` Visualiza de mejor manera el contenido declarado<br>
`console.table() ` Visualiza de manera grafica una tabla, con el contenido declarado<br>

# Consejos con el console

Una de las mejores formas y mas reconmendables de visualizar contendo detallado de los console's ya sea variable, cadenas , etc. Es agragando { } llaves al contenido declarado en el console: <br>
`console.log({})` <br>
Este serviria para visualizar el nombre de la variable, cadena, u objeto desde que se declara, todo para ahorro de escritura.<br> <br>
Una forma de agregar estilos a los console dentro del navegador seria de la siguiente forma : <br>
`console.log('%c Mis variables' , 'color: white; font-weight:bold');`
<br>

# Orden y consejos de ubicaciones

Parte de las buenas practicas es crear carpeta de recursos: <br>
`assets/` <br>
la importancia de crear este tipo de carpetas conforme el nombre es para que en frameworks futuros esto se indica como forma estandarizada y dentro de ingresar las mismas carpetas a utilizar ya sea <br> `css/` <br> `js/` <br> `sass/` <br> Etcetera

# prompt, confirm y alert

3 Tipos de forma de ingreso de informacion de usuario <br>
La primera de ellas es el: <br>
`alert('Hola mundo')` <br>
El alert es un mensaje flotante que detiene la ejecucion de la pagina hasta que aceptes el mensaje dentro de el.<br><br>
El segundo de ellos es el: <br>
`prompt('Cual es tu nombre? ', 'Sin nombre')`
El prompt consta de una caja en el cual puedes recibir un valor y almacenarlo en una variable, consta de 2 parametros mensaje y valor por defecto , ya sea en el caso del receptor un valor por defecto como el 'Sin nombre' o espacio en blanco <br>
Para almacenar dicho resultado del valor escrito en la caja de texto , se almacena de la siguiente manera: <br>
` let nombre = prompt("Cual es tu nombre? ", "Sin nombre");` <br><br>
El tercero de ellos es el: <br>
`confirm('Esta seguro de borrar esto?')`
El confirm consta de un mensaje y botones de aceptar y cancelar , dado el ejemplo de prompt, este es almacenable en una variable , pero solo regresa valores booleanos (true, false), true aceptando el mensaje y false cancelando el mensaje , estos a su vez pueden guardarse de la manera siguiente: <br>
`const seleccion = confirm('Esta seguro de borrar esto?')` <br><br>
Nota:Los 3 tipos de ingreso , son metodos del objeto window (objeto del leguaje de programacion javascript) <br>

# Tipo de dato de una variable

Describle el contenido del valor que tiene la variable

## Primitivos

Es una informacion que no es un objeto y son inmutables <br>

> Boolean - true / false :: Verdadero y falso <br>
> Null - Sin valor en lo absoluto <br>
> Undefined - Una variable declarada que aun no se le asigna valor <br>
> Number - integers, floats, etc. <br>
> String - Una cedena de carateres, ej: Palabras, nombres de personas<br>
> Symbol - Es un valor unico que no es igual a ningun otro valor <br>

Parte del dia a dia es la forma de saber que tipo de dato es una variable , pero cuando no tengamos alguna referencia a ello podemos utilizar el: type of <br>
`console.log(typeof nombre);` <br>
Consta de la palabra reservada y la variable a evaluar <br>

# Palabras reservadas y nombre de variables

Son palabras que tienen un uso especifico. <br>
No utilizar nombres de variables que lleven caracteres especiales.

# Arreglos

Son un objeto muy parecido a una lista de informacion , que contienen un grupo de elementos, Usualmente , esa informacion dentro del arreglo es del mismo tipo de dato. <br>
`[ ]` <br>
Cada vez que se mire llaves [ ] en javascript esto es un arreglo.<br>
Formas de inicializar arreglos en javascript: <br><br>
`const arr = new Array(10);` <br>
Este forma crea un arreglo con 10 espacios , es muy raro de verlo pero existe. <br><br>
`const arr = [];`<br>
Esta forma es la manera mas comun de hacerlo dado que se inicializa un arreglo pero de forma dinamica , no dandole un espacio ya determinado al arreglo. <br><br>
En javascript tiene la peculiaridad que los arreglos son muy flexibles , ejem: <br>

```
let arregloCosas = [
  true,
  123,
  "Fernando",
  1 + 2,
  function () {},
  () => {},
  { a: 1 },
  ["X", "Megaman", "Zero", "Dr.Light", ["Dr. Willy", "Woodman"]],
];
```

# Metodos en Javascript utiles que usar

El arreglo puedo llevar desde funciones hasta otros arreglos. <br>
Explicando un poco los arreglos , nos encontramos con metodos que son muy utilices en el lenguaje JS, uno de ellos es el length. <br>
`.length` <br>
El .length permite obtener la suma de los elementos en un arreglo ejemplo: <br>
`let juegos = ["Zelda", "Mario", "Metroid", "Chrono"];`<br>
El numero del contenido dentro del arreglo de juegos es 4 , nombrandolo de la siguiente manera:
`juegos.length`<br><br>
Otra de los Metodos incluidos dentro de JS es el forEach( ) . El metodo sirve de tal manera que va a ejecutar una instruccion por cada uno de los elementos en el arreglo:<br>
`juegos.forEach()` <br>
En el caso anterio la instruccionseria la siguiente: <br>

```
juegos.forEach((elemento, indice, arr) => {
    console.log({elemento, indice , arr});
});
```

El codigo anterior trabaja de la siguiente forma, destro de los parentesis el elemento dicta el valor de la posicion que cicle el for , el indice seria la posicion en la que clicle el for ,y el arr apunta a la descripcion del arreglo en la posicion en la que cicle el for, es decir dando el siguiente resultado: <br>
`{elemento: 'Zelda', indice: 0, arr: Array(4)}`<br>
`{elemento: 'Mario', indice: 1, arr: Array(4)}`<br>
`{elemento: 'Metroid', indice: 2, arr: Array(4)}`<br>
`{elemento: 'Chrono', indice: 3, arr: Array(4)}`<br><br>
Otro metodo comun es el de añadir un elemento al arreglo: <br>
`juegos.push()`<br>
Ejemplo: <br>
`juegos.push('F-zero')` <br>
Y el resultado seria : <br>
`(5) ['Zelda', 'Mario', 'Metroid', 'Chrono', 'F-Zero']`<br>
Pero este arreglo tambien regresa un .length una longitud,que se visualiza en el primero elemento el (5), y que puede ser almacenado en una variable
<br><br>
Para agregar un elemento al inicio y no al final como el .push se utiliza el: <br>
`juegos.unshift('Fire Emblem');`<br><br>
Para eliminar el ultimo elemento en un arreglo y almacenar el ultimo elemento borrado en una variable seria: <br>
`let juegoBorrado = juegos.pop();` <br><br>
Para eliminar elementos especificos dentro del arreglo se hace se la siguiente forma:

```
let pos = 1;
console.log(juegos);
let juegosBorrados = juegos.splice(pos, 2)
```

El .slice recibe 2 parametros , el primero la posicion desde que se hara el borrado y el segundo la cantidad de espacios en el array por borrar y retorna por defecto los elementos borrados
<br> <br>
Para buscar la posicion de un elemento en el arreglo seria: <br>
`let metroIndex = juegos.indexOf("Metroid");` <br>
De esta forma almacena en la variable la posicion ,y se necesita el valor ah buscar en el arreglo

# Objetos literales

`let personaje = {};`  
Cada vez que se vean las { } llaves en JS, esta asociado a un objeto.  
Los objetos literales tienden a trabajar de forma flexible en JS, como lo vimos en los arreglos.

```
let personaje = {
  nombre: "Tony Stark",
  codeName: "Ironman",
  vivo: false,
  edad: 40,
  coords: {
    lat: 34.04,
    lng: -118.7,
  },
  trajes: ["Mark I", "Mark V", "Hulkbuster"],
  direccion: {
    zip: "10880, 90265",
    ubicacion: "Malibu, California",
  },
  'ultima-pelicula': 'Infinity war',
};
```

Para imprimir todo el objeto:  
`console.log(personaje);`  
Para imprimir el nombre de Tony Stark:  
`console.log("Nombre:", personaje.nombre);`  
Para imprimir el nombre de Tony Stark de diferente forma seria:  
`console.log("Nombre:", personaje["nombre"]);`  
Para imprimir la edad:  
`console.log("Edad:", personaje.edad);`  
Para imprimir cordenadas:  
`console.log("Cordenadas:", personaje.coords);`  
Para imprimir latitud del objeto cordenadas:  
`console.log("Latitud:", personaje.coords.lat)`  
Para imprimir la cantidad de trajes del arreglo incluido en el objeto:  
`console.log("No. Trajes:", personaje.trajes.length);`  
Para imprimir y calcular dentro de un objeto, en este caso el ultimo traje del personaje:  
`console.log("Ultimo Traje:", personaje.trajes[personaje.trajes.length - 1]);`

Formas de utilizar una variable con un objeto:

```
const x = "vivo";
console.log("Esta vivo?:", personaje[x]);
```

Como se demostro en la diferente forma de imprimir el nombre, utilizamos una variable para remplazar el parametro del objeto deseado.  
 Nota: Una forma de incluir dos palabras en un objeto seria encerrandolos en corchetes:  
 ` 'ultima-pelicula': 'Infinity war',`  
 y para imprimirla:  
 `console.log('Ultima Pelicula', personaje["ultima-pelicula"]);`

## Mas Detalles

Para eliminar un propiedad en objetos :  
`delete personaje.edad;`

Para poder intertar una nueva propiedad en los objetos se utiliza:  
`personaje.casado = true;`

Para poder convertir objeto en un arreglo:  
`const entriesPares = Object.entries(personaje);`

Para poder bloquear modificaciones en el objeto:  
`Object.freeze(personaje);`

Para convertir en arreglo unicamente los nombres de las propiedades
`const propiedades = Object.getOwnPropertyNames(personaje);`

Y para convertir en arreglo unicamente los valores de las propiedades  
`const valores = Object.values(personaje);`
****