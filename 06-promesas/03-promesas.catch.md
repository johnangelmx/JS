# Promise.prototype.catch()

El método catch() retorna una Promise y solo se ejecuta en los casos en los que la promesa se marca como Reject. Se comporta igual que al llamar Promise.prototype.then(undefined, onRejected) (de hecho, al llamar obj.catch(onRejected) internamente llama a obj.then(undefined, onRejected)).

Síntaxis

```
p.catch(onRejected);

p.catch(function(reason) {
   // rejection
});
```

Es decir, el catch es el metodo que recibe el error que nosotros hemos que se dispararia, el **reject**. Pero este metodo tiene sus excepcion al contrario del `.then` en el `Promise.all()`, el catch recive el error, pero no recibe mas de un argumento , es decir que si tenemos dos errores este solo retornara el primero y dejara de ejecutar la promesa, esto funciona por defecto.  
Ejemplifiquemoslo:

```
Promise.all([buscarHeroe(heroeId1),buscarHeroe(heroeId2)])`.then(([heroe1,heroe2]) => {
    console.warn(`Enviando a ${heroe1.nombre} y ${heroe2.nombre} a la misison`)
}).catch(error => {
    alert(error)
})
```
El `.catch` podemos adherirlo al `Promise.all`, de esta forma teniendo no solo la resolucion efectiva de las promesas si no tambien los errores y que hacer en caso de que este no se cumpla, teniendo como argumeto lo retornado por el **rejec**. 
Teniendo en el navegaro una alerta con el mensaje:  
`No existe un heroe con el id`  

de este forma podemos definir una accion al tener un error.