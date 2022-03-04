# Callbacks

Una función de callback es una función que se pasa a otra función como un argumento, que luego se invoca dentro de la función externa para completar algún tipo de rutina o acción.  
Es decir, una funcion que se manda como argumento dentro de otra funcion.

Sintaxis basica enviando funcion:

```
function methodName (arguments, callback) {
    // body
    callback(arguments)
}
```

Parte de la metodologia estandar ah usar el callback debe ser declarado como argumento , cuando se inicia la funcion , y el nombre "**callback**" puede ser cambiado por otro pero por estandar es mejor llamarlo por lo que es.

Y este mismo como si fuerea un **return** , retorna argumentos o procesos , que pueden ser llamados y manipulados en donde se este recibiendo este callback

Sintaxis basica recibiendo funcion:

```
functionName(arguments ,(argumentsCallback)=>{
    //body
})
```

Al momento de invocar la funcion todo es secuencial , es decir, envia los argumentos , se completa la accion dentro de la funcion y devuelve la respuesta del callback a la otra funcion , haciendo posible usar los argumentos enviados por el callback , asi teniendo otra manipulacion en la funcion llamada por el callback , ejemplo:

# Buscar heroe e imprimir heroe usando callbacks

varibles a usar:

```
const heroeId = 'capi2'
```

Base no relacional

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
    spidr: {
        nombre: 'Spiderman',
        poder: 'La mejor reaccion alergica a las picaduras de araña'
    },
}

```

Planteemos el siguiente callback , teniendo en cuanta que hay que elaborar al funcion de la funcion que estamos haciendo, es decir , elaboremos la primera funcion, esa que envia como argumento otra funcion.

```
buscarHeroe(heroeId, () => {

})
```

Como podemos observar es una simple y sencilla funcion que como argumento tiene el **heroeId** que vamos a enviar para buscar y como segundo argumento tenemos una funcion de flecha invocada, es decir en en momento que se inicia la funcion **buscar heroe** tamien se inicia esta funcion de fecla, que por nombre y estadarizacion este se le conoce como el callback.

Ahora crearemos el la funcion buscar heroe con los argumentos que se estan enviando

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]
    callback(heroe)
}
```

Examinemos paso por paso:

```
const buscarHeroe =(id,callback) =>{

}
```

Como podemos ver la creacion de la funcion es por medio de flecha , y asu vez tenemos que los argumento son **id**, que le enviaremos **heroeId** y **callback** que le enviaremos **la funcion de flecha (callback)** .

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]

}
```

Pero como habiamos menciona es una funcion que buscara un heroe , asi que la linea `const heroe = heroe[id]` hace alusion como si estuvieramos haciendo `const heroe = heroe['capi']`, podemos ver que se llama de forma de un arreglo , pero tambien funciona con objetos este tipo de llamado.

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]
    callback(heroe)
}

```

Y por ultimo tenemos el callback, que funciona como un return , es decir que puede enviar argumetos a la primera funcion que lo estamos invocando en este caso lo estamos enviando el resultado de la busqueda, teniendo asi la opcion de manipular el argumento enviado por el callback en la primera funcion en el cual lo estamos llamando , imprimiendo el nombre del heroe identificado:

```
buscarHeroe(heroeId, (heroeDelCallback) => {
    console.log(heroeDelCallback)
})
```

teniendo como resultado :  
`{ nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir' }`
