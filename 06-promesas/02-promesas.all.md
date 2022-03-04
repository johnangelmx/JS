# Promesas.All

Como vimos en apartado callback hell, las peticiones multiples dentro de callbacks, se hacian inleibles, lo cual traia problemas, plantiemos el mismo problema con en el ejemplo anterior

```
buscarHeroe(heroeId1).then(heroe1 =>{
    buscarHeroe(heroeId2).then(heroe2 =>{
        console.warn(`Enviando a ${heroe1.nombre} y ${heroe2.nombre} a la misison`);
     })
    })
})
```

Como podemos ver el problema sigue, siendo el caso como las callback , las promesas de igual manera llegaran a un momento en el cual sera inleible y tendremos mucho codigo intangible. Para ello en las promesas hay un metodo , en el cual podemos hacer lo anterior pero de una manera ordenada

# Promise.all()

El método Promise.all(iterable) devuelve una promesa que termina correctamente cuando todas las promesas en el argumento iterable han sido concluídas con éxito, o bien rechaza la petición con el motivo pasado por la primera promesa que es rechazada.  
Sintaxis:

```
Promise.all(iterable);
```

Es decir , que de igual manera que el `.then()` este podra obtener ejecutarse si la promesa, en este promesas fueron cumplidas.  
Y para poder utilizarlo tenemos que organizar nuestras llamada de la promesa a un arreglo:

```
Promise.all([buscarHeroe(heroeId1),buscarHeroe(heroeId2)])
```

Una vez creado el arreglo podemos definir el caso en el cual todas las promesas sean cumplidas con el `.then()`:

```
Promise.all([buscarHeroe(heroeId1),buscarHeroe(heroeId2)])`.then(heroes => {
    console.warn(`Enviando a ${heroes[0].nombre} y ${heroes[1].nombre} a la misison`);
})
```

Pero en este caso , tendremos que tomar los objetos como un el arreglo que son y utilizarlos en la posicion correspondiente

# Desestructuracion de elementos

Como anteriormente vimos la desucstructarion de elemento nos sirve para utilizar de mejor manera los valores individuales de un arreglo o un objeto, para ello podemos utilizarlos en este caso.

Y al ser un arreglo la desestructuracion de hace con **[ ]**:

```
Promise.all([buscarHeroe(heroeId1),buscarHeroe(heroeId2)])`.then(([heroe1,heroe2]) => {
    console.warn(`Enviando a ${heroe1.nombre} y ${heroe2.nombre} a la misison`)
})
```
Teniendo en cuenta que esta desestructuracion tiene que ser encerrado con **( )**
para no tener erroes y definiendolo como una expresion dentro de la promesa, podemos ver que conforme fue declarada en el `Promise.all` son desestructuradas en la misma posicion el heroe1 y el heroe2 , teniendo el mismo resultado