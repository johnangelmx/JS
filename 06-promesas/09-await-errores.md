# await error
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


```
const obtenerHeroeAwait = async (id) => {
    try {
        const heroe = await buscarHeroeAsync(id)
        return heroe
    } catch (error) {
        console.warn('CATCH!!!');
        // throw error;
        return {
            nombre: 'sin nombre',
            poder: 'sin poder'
        }
    }
}
```

Evaluemos el siguiente codigo , para lo consiguiente tenemos un manejo de excepcion es decir de respuesta negativas del await, y cabe recalcar que es del await y no de la promesa:

```
obtenerHeroeAwait('capi1')
    .then(heroe => {
        console.log(heroe)
    }).catch(console.warn)
```

El try y el catch , de la funcion permite lo que mencionabamos, que pasa si queremos poner un excepcion en el await y no en la promesa que estamos llamando?

try { Permite enviar si todo sale sin problemas , vaya sin ninguna excepcion u erro en la promesa}.

catch(error){ Si existe alguna excepcion inmediatamente saltara al catch y retornara lo que se le indique , ya se el throw del error, o un objeto con condiciones vacias , esto para no perder la forma en la cual se trabaja}

si se envia un throw , este caera en el .catch() de la funcion principal.  
y si se envia un return, este caera en el .then() de la funcion principal
