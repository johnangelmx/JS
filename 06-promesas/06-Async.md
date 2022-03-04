# Async

Como hemos visto las promesas tiene su funcion al llamado de una funcion y la creacion de otra, es decir, su implementacion esta definida para obtener respuestas concretas a casos positivos u negativos.

Pero exite una forma mas reducida de hacer una promesa por medio del `async`

### Async

La declaración de función async define una función asíncrona

### asíncrona

El término asíncrono se refiere al concepto de que más de una cosa ocurre al mismo tiempo, o múltiples cosas relacionadas ocurren sin esperar a que la previa se haya completado.

Teniendo en cuenta lo anterior dicho planteemos la forma de reducir un promesa:

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

El codigo hace referencia a ejemplo de esta guia, en el apartado de promesa. Como bien sabemos las promesas constan que en el return sea definido el resolve y el reject, pero existe una forma mas corta para implementarlo:

```
const buscarHeroeAsync = async (id) => {
    const heroe = heroes[id]

    if (heroe) {
        return heroe // se puede enviar varios argumentos
    } else {
        throw `No existe un heroe con el id ${id}`
        // throw Error(`No existe un heroe con el id ${id}`)
    }
}
```

Observemos que el primer cambio es el añadido de `async` antes de la declaracion de argumentos, esto es un estandar a seguir para las promesas asíncrona.

Para poder comprender de mejor manera como es que se envian el `resolve` y el `reject`, tendremos que estarizar el `resolve` como `return` y y el `reject` como el `throw`,es decir:

## resolve:

`return heroe // se puede enviar varios argumentos`

## reject:

`throw No existe un heroe con el id ${id}`

Pero en el caso de throw si no tenemos un mensaje de error o no sabemos de donde viene el error tendremso que agregar el `Error()` dentro del trown asi obteniendo un mensaje mas claro del problema:

## reject with Error:

`throw Error(No existe un heroe con el id ${id})`
