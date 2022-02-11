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

El `.slice` recibe 2 parametros , el primero la posicion desde que se hara el borrado y el segundo la cantidad de espacios en el array por borrar y retorna por defecto los elementos borrados
<br> <br>
Para buscar la posicion de un elemento en el arreglo seria: <br>
`let metroIndex = juegos.indexOf("Metroid");` <br>
De esta forma almacena en la variable la posicion ,y se necesita el valor ah buscar en el arreglo
