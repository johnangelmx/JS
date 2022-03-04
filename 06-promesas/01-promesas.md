# Promesas

Las promesa son como la expresion que hacemos en la vida real, es decir, yo te prometo algo en un determinado momento de entrega y puedo tener una respuesta resulta o una respuesta rechazada,osea no cumplida.  
En Javascript esto se maneja de una forma en la cual resuelve los problemas que tenemos en los **callbacks**, en el caso de manejo de errores en los cuales nosotros teniamos que manejar eso y no el propio lenguaje, en el caso de las promesas ese manejo lo llevan las mismas.

Tomando el ejemplo anterior, creeamos un problema y planteamos los procesos de las promesas

# Buscar heroe e imprimir heroe usando promesas

Variables a usar:

```
const heroeId1 = 'capi'
const heroeId2 = 'spider'
const heroeId3 = 'iron'
```

Base de datos no realacional:

```
const heroes = {
    capi: {
        nombre: 'Capitan America',
        poder: 'Aguantar inyecciones sin morir'
    },
    iron: {
        nombre: 'Ironman',
        poder: 'Absurda cantidad de dinero'
    },
    spider: {
        nombre: 'Spiderman',
        poder: 'La mejor reaccion alergica a las picaduras de araña'
    },
}
```

A diferencia del apartado pasado , en este caso inciaremos con la estructura de una promesa, sintaxis basica:

```
const functionName = (arguments) =>{
    //body
    return new Promise((resolve,reject)=>{
        //body Promise
    })
}
```

Como primer caso y comun se crea un funcion de flecha, el cual recibe argumentos y tiene un body , normal y corriente.  
`return new Promise((resolve,reject)=>{ //body Promise })`  
El return se trabaja de manera diferente dejando en claro que lo que retorna es una nueva instacia de una promesa el cual contiene 2 palabras reservadas importantes el `resolve,reject`:

## resolve

La palabra reservada resolve en las promesas dicta que dicha situacion esta resulta , que si se usa el resolve , es porque la promesa se cumplio

## reject

La palabra reservada reject en las promesas dicta que dicha situacion no esta resuelta, que si se usa el reject , es porque la promesa no se cumplío.

Hasta este punto usar las palabras reservadas ayudara al codigo a facilitar el resultado de la operacion , en este caso resolver si el heroe esta en la base de datos, teniendo como resultado el siguiente codigo:

```
const buscarHeroe = (id) => {
    const heroe = heroes[id]


    return new Promise((resolve, reject) => {
        if (heroe) {
            resolve(heroe) // se puede enviar varios argumentos
        } else {
            reject(`No existe un heroe con el id ${id}`)
        }
    })
}

```

Planteado consiguiete, si el heroe es un true, es decir tiene almacenado algo que no sea un `undefined,null, false` entoces tomaremos la palabara reservada resolve y le enviaremos como argumento el objeto heroe, el cual almacena el objeto que se identifico. Nota: se puede enviar mas de un argumento en el apartado resolve.

Pero, si no tenemos el heroe en la base de datos,o se busco de manera incorecta entonces optaremos por el reject , el cual es una palabra reservada,que como argumento enviamos un string con el texto "**No existe un heroe con el id**" y con el id enviado como argumento.

Hasta este punto ya tenemos planteado varias cosas del Promise, como el que pasa si se cumple(**resolve**), que pasi si no se cumple(**reject**) y su sintaxis basica en funcionamiento de una funcion con su debido return. Ahora bien como lo utilizamos del lado en el cual lo llamamos?

# Llamando la promesa

Para poder utilizar la promesa primero mandamos a llamar la funcion como comun mente lo hacemos :

```
buscarHeroe(heroeId1)
```

Despues accedemos a la promesa por medio de la instacia que hicimos, vaya! como lo hicieramos como un objeto y tendremos 3 opciones dentro de la promesa a utilizar que serian el , `then, catch , finally`

# Then

El método `then()` retorna una Promesa. Recibe dos argumentos: funciones callback para los casos de éxito y fallo de Promise.

En pocas palabras si se cumple la promesa , con el `.then()` podemos recibir el argumento que se envio en el `resolve` y asu vez manipularlo para hacer una accion en ese momento.

```
buscarHeroe(heroeId1).then(heroe => {
    console.log(`Enviando a ${heroe.nombre} a la mision`)
})

```
En este caso recibimos el argumento que es un objeto heroe y lo utilizamos en el callback, en la funcion dentro de la funcion que se dispara al momento que se resulve la promesa, dicho asi ejemplificado , sabemos que si existe el heroe, el `.then()`recibe el heroe e imprimos con la propiedad nombre el heroe a la mision .



