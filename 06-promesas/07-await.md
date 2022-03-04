# await

Para poder comprende el await tenemos que retomar el signifado de asincrona

### asíncrona

El término asíncrono se refiere al concepto de que más de una cosa ocurre al mismo tiempo, o múltiples cosas relacionadas ocurren sin esperar a que la previa se haya completado.

## await

El operador await es usado para esperar a una Promise. Sólo puede ser usado dentro de una función async function.
Es decir permite la espera de la respuesta de una promesa, siendo asi un resultado mejor controlado para la manipulacion de la misma.  
Ejemplo , Codigo a evaluar:

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

Tenemos el ejemplo anterior, de una promesa asincrona , el cual recibe un id y este retornara el objeto del id, o un error del mismo.

```
const heroesIds = ['capi', 'iron', 'spider',]
```

Ahora digamos que tenemos este arreglo de id's ,que seran evaluado por la funcion-promesa anterior planteada.

```
const obtenerHeroesArr = () => {
    const heroesArr = []
    for (const id of heroesIds) {
        buscarHeroeAsync(id).then(heroe => heroesArr.push(heroe))
    }
    return heroesArr
}
```

Tendremos como consiguiente la funcion la cual crea un nuevo array, y barre el arreglo con la condicion de buscar en la funcion `buscarHeroeAsync` , e introducirlos al nuevo arreglo obtenido , retornando asi el nuevo arreglo realizado

```
const heroesArreglo =  obtenerHeroesArr()
console.log(heroesArreglo)
```

Teniendo como resultado:  
`> [ ]`  
Pero al darle click al arreglo se despliega:

```
>[]
> 0: {nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
> 1: {nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
> 2: {nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}`
```

## Analizando el problema

Lo que pudimos ver es que las promesas se resolvieron despues de invocar la funcion , esto puede ser un problema muy grande dado que al trabajar con base de datos ,queremos que los datos sean visualizados al mismo tiempo que hacemosla peticion , no despues cuando la promesa sea respondida, para ello tenemos el `await`

Ejemplo:  
Para poder resolver el problema anterior tendremos que replantear algunas cosas

```
const obtenerHeroesArr = async() => {
    const heroesArr = []
    for (const id of heroesIds) {
        const heroe = await buscarHeroeAsync(id)
        heroesArr.push(heroe)
    }
    return heroesArr
```

El primer cambio significativo es que la funcion se declara como **asíncrona** dado que el await solo trabaja con funciones asi , y como ya habiamos explicado, la funcion **asíncrona** se refiere al concepto de que más de una cosa ocurre al mismo tiempo para ello se declara antes de los argumentos.

` const heroe = await buscarHeroeAsync(id)`  
En este apartado es donde el await hace su entrada , es decir , este creara la instruccion que para asignar lo que se le pide , tiene que esperar la respuesta de la promesa, solo asi podra ser asignada, no importa el resultado de la misma ya se positiva o negativa esperara la respuesta para ser asignado a la variable creada

` heroesArr.push(heroe)`  
Y en este fragmento una vez con la respuesta obtenida ,ya podremos ingresarlo al nuevo arreglo para retornalo al final del barrido

# funcion asíncrona

Cuando volvemos una funcion , en funcion asíncrona , este ya no es una funcion normal ,esta se vuelve una promesa. por ello la instruccion anterior de impresion:

```
const heroesArreglo =  obtenerHeroesArr()
console.log(heroesArreglo)
```

Ya no es valida! , dado que el resultado es:

```
> Promise {<pending>}
[[Prototype]]: Promise
[[PromiseState]]: "fulfilled"
[[PromiseResult]]: Array(3)
```

Esto indica que lo que estamos imprimiendo es la Promesa y su resultado ,mas no el contenido de la misma.

## Async

Como se menciono al ser una funcion asíncrona se vuelve una Promesa, asi que para imprimir el resultado de la misma es de la misma forma de las promesas comunes:

```
obtenerHeroesArr().then(console.log)
```

Teniendo como resultado:

```
>(3) [{…}, {…}, {…}]
  >0: {nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
  >1: {nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
  >2: {nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}
```

De esta forma pudimos descubrir el funcionamiento del await y sus benificios ,cabe resaltar que de esta forma podremos visualizar en tiempo y forma la peticion de las promesas