# Promise.prototype.finally()

El método finally() devuelve una Promise. Cuando la promesa se resuelve, sea exitosa o rechazada, la función de callback específicada será ejecutada. Esto ofrece una forma de ejecutar código sin importar como se haya resuelto la promesa.

Esto ayuda a evitar tener código duplicado tanto en el then() como en el catch().

### Sintaxis

```
p.finally(alFinalizar);

p.finally(function() {
   // finalizada (exitosa o rechazada)
});
```

Es decir , que el `.finally()` permite ejecutar un codigo relacionado con la promesa, pero sin tomar en cuanta si ,se resolvio o no.

Ejemplifiquemoslo:

```
Promise.all([buscarHeroe(heroeId1),buscarHeroe(heroeId2)])`.then(([heroe1,heroe2]) => {
    console.warn(`Enviando a ${heroe1.nombre} y ${heroe2.nombre} a la misison`)
}).catch(error => {
    alert(error)
}).finally(()=>{
   console.log('Finally')
})
```

El `.finally()` se puede adherir al `Promise.all`,y este no recive argumento y se ejecutara al final de la promesa cual se el resultado de la promesa, teniendo el siguiente resultado:  
`>Finally`
Esta ejecucion sirve mas en el panorama de tareas que no se cumplieron en un tiempo determinado ,ya sea el enviado de un email o el error en un serividor
