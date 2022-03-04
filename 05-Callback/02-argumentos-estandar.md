# Argumentos Estandar De Los Callbacks

Tomando el ejemplo anterior, tendremos que hacer el manejo de errores:  
Varibles a usar:

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

Codigo a usar:

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]
    callback(heroe)
}

```

Callback:

```
buscarHeroe(heroeId, (heroeDelCallback) => {
    console.log(heroeDelCallback)
})
```

# Manejo de erroes

Teniendo en cuenta la entandarizacion de los callbacks, el manejor de errores es algo que viene por defecto.  
Planteemos que nos envian un **heroId** Que no existe , para ello tendriamos que crear un manejo de errores tal vez generico , como un `if-else` o un manejo de `switch`, pero no es necesario del todo, ya como habiamos dicho, el manejo de errores es un estandar al momento de usar callback.

Manejemoslo el error como un argumento en el callback, es decir tendriamos el error y el argumento del callback que si es valido

Codigo a usar:

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]
    if (heroe){

    }else {
        //Manejo de error
        callback(`No existe el heroe ${id}`)
    }

}
```

Callback:

```
buscarHeroe(heroeId, (err,heroeDelCallback) => {
    if(err){
        console.error(err)
    }else {

    }

})
```

Tomemos en cuenta lo anterior, la forma en la cual estamos manejando el error, es aquella que el callback siempre enviara como primer argumeto el erro **err** y como segundo argumento el resultado del callback si no hay erroes, entonces de esta forma teniendo dos estructuras de control que estan atentas a errores, asi si no tenemos un id encontrado enviamos el siguiente mensaje:  
`No existe el heroe capi 2`  
Y si no tenemos errores tendremos el siguiente codigo:  
Codigo a usar:

```
const buscarHeroe =(id,callback) =>{
    const heroe = heroe[id]
    if (heroe){
        callback(null, heroe)
    }else {
        //Manejo de error
        callback(`No existe el heroe ${id}`)
    }

}
```

Callback:

```
buscarHeroe(heroeId, (err,heroeDelCallback) => {
    if(err){
        console.error(err)
    }else {
        console.log(heroeDelCallback)
    }

})
```

Teniendo asi el hecho que en el if del callback al ver que el error no es `true`, significa que el null entro y el heroeDelCallback se toma encuenta
