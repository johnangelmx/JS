# Pro Tip Await

Manejo del tiempo en funciones asíncronas.  
Parte de hacer la promesas es que no sabemos el tiempo en el cual un servidor espera por peticion , pueden ser 1 segundo 2,3 etc, pero digamos que tenemos la de un segundo , y hacemos el ejemplo anterior :

```
const buscarHeroe = (id) => {
    const heroe = heroes[id]


    return new Promise((resolve, reject) => {
        if (heroe) {
            setTimeOut(()=>{
                resolve(heroe) // se puede enviar varios argumentos
            },1000)
            resolve(heroe) // se puede enviar varios argumentos
        } else {
            reject(`No existe un heroe con el id ${id}`)
        }
    })
}
```

usaremos la peticion promesa que no es asincrona para visualizar mejor si tenemos un servidor que espera un segundo por peticon por ello ingresamos un timeout(de un segundo) .

```
const heroesIds = ['capi', 'iron', 'spider',]
```

```
const obtenerHeroesArr = async() => {
    const heroesArr = []
    for (const id of heroesIds) {
        const heroe = await buscarHeroe(id)
        heroesArr.push(heroe)
    }
    return heroesArr
```

Con ello tendriamos el problema antes mencionado , la impresion de la misma tarda 3 segundo en aparecer , esto porque por peticion tarda 1 segundo en nuestro servidor

# Arreglando los tiempos de peticion

```
const obtenerHeroesArr = async () => {
    const heroesArr = []
    for (const id of heroesIds) {
        heroesArr.push(buscarHeroe(id))

    }
    return await Promise.all(heroesArr)
}
```

Analicemos el codigo optimizado, para ello observamos que lo que haremos es un arreglo de promesas con la instruccion:  
` heroesArr.push(buscarHeroe(id))`  
esto imprime:

```
obtenerHeroesArr().then(console.log)
```

```
>(3) [Promise, Promise, Promise]
	>0: Promise {<fulfilled>: {…}}
	>1: Promise {<fulfilled>: {…}}
	>2: Promise {<fulfilled>: {…}}
```

un arreglo de promesas y anteriormente ya conocemos una forma de usar un arreglo de promesas y manipular su contenido para ser leible su contenido, asi es con el **Promise.all** por ellos la siguiente instruccion retornara el contenido de dichas promesas reduciendo su tiempo de ejecucion:  
`return await Promise.all(heroesArr)`  
Como podemos observar puede ser incluido el `await` dado que sigue siendo un peticion asíncrona siendo asi la siguiente impresion:

```
obtenerHeroesArr().then(console.log)
```

```
>(3) [{…}, {…}, {…}]
    >0: {nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
    >1: {nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
    >2: {nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}
```

Siendo asi el tiempo de ejecucion en:  
`await: 1001.6630859375 ms`

# Optimizando codigo

```
const obtenerHeroesArr = async () => await Promise.all(heroesIds.map(buscarHeroe))
```

el siguiente codigo es una sola linea, se incializa como cualquier variable pero el retorno de la misma comienza con el `await` que hace alucion al `promise.all`, que dento de el sabemos que recibe un arreglo de promesas y el arreglo de promesas es retornado por un `.map`.

Como sabemos el `.map` recibe un arreglo y retorna un arreglo nuevo barriendo cada uno por una funcion y en ese caso la funcion a evaluar es aquella que regresara una promesa por cada elemento del arreglo , y asi es en este caso usaremos la funcion-promesa `buscarHeroe` , que no hace falta decir el argumeto ya que esto:

`.map( id => buscarHeroe(id))` **es igual a** `.map(buscarHeroe)`
teniendo como resultado la funcion asíncronica anterior.

## En pocas palabras esto:

```
const obtenerHeroesArr = async () => await Promise.all(heroesIds.map(buscarHeroe))
```

## Es igual a esto:

```
const obtenerHeroesArr = async () => {
    const heroesArr = []
    for (const id of heroesIds) {
        heroesArr.push(buscarHeroe(id))

    }
    return await Promise.all(heroesArr)
}
```
