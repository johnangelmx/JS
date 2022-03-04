# Callback Hell

El callbackHell es nada mas y nada menos que la forma en la cual se anida multiples callbacks todo esto para tener multiple informacion que se pueda utilizar en el mismo fragmento de codigo

```


const heroeId1 = 'capi'
const heroeId2 = 'spider'
const heroeId3 = 'iron'


// una funcion ,mandar como argumento. Es una funcion que es mandada como un argumento
buscarHeroe(heroeId1, (err, heroe1) => {
    if (err) return console.error(err)

    buscarHeroe(heroeId2, (err, heroe2) => {
        if (err) return console.error(err)

        buscarHeroe(heroeId3, (err, heroe3) => {
            if (err) return console.error(err)
            
            console.warn(`Enviando a ${heroe1.nombre},  ${heroe2.nombre} y ${heroe3.nombre} a la mision`)
        })
    })

})
```
Como pedome visualizar lo que tenemos es un callback anidado , en el cual usamos la funcion/callback **buscarHeroe**, para poder imprimir una instruccion pero hacemos multiples busquedas y por eso tenemos un callback anidado, que como resultado tenemos la impresion:  
` Enviando a Capitan America,  Spiderman y Ironman a la mision`  
Pero el codigo es inleíble.  
Pare ello se crearon las promesas , apartado en el siguiente documento...
