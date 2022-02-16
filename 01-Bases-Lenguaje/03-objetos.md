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