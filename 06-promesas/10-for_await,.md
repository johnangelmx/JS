# For con await
Como planteamiento del problema, digamos que tenemos un arreglo de promesas:
```
const heroesPromesas = heroesIds.map(buscarHeroe)
```
Y que tenemos que imprimir cada uno de ellos de la forma posible: 
```
const heroesCiclo = async () => {
    console.time('heroesC');

    const heroes = await Promise.all(heroesPromesas)
    console.log(heroes)
    console.timeEnd('heroesC');
}
```

```
heroesCiclo()
```

```
(3) [{…}, {…}, {…}]
0: {nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
1: {nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
2: {nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}
```
Como podemos observar en una variable guardamos el arreglo de objetos ya creados por el `Promise.all` y lo mandamos a imprimir ya que obtenemos el arreglo con los objetos incluidos, pero ese no es lo que necesitabamos , nostros necesitabamos la impresion individual de ellos...

For each
---

```
const heroesCiclo = async () => {
    console.time('heroesC');

    const heroes = await Promise.all(heroesPromesas)
    heroes.forEach(console.log)
    console.timeEnd('heroesC');
}
```

```
heroesCiclo()
```

```
>{nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
>{nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
>{nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}
```
Una forma de hacerlo, es con el `.forEach()`, el cual permite barrer cada elemento del arreglo asi imprimiendo cada elemento de forma de individual , aun que si es lo que buscamos no es la forma en la cual sea por proceso indivual, es decir , que resulva la promesa e imprima por la misma 

# For await
---

```
const heroesCiclo = async () => {
    console.time('heroesC');
    for await (const heroe of heroesPromesas) {
        console.log(heroe)
    }
    console.timeEnd('heroesC');
}
```

```
heroesCiclo()
```

```
>{nombre: 'Capitan America', poder: 'Aguantar inyecciones sin morir'}
>{nombre: 'Ironman', poder: 'Absurda cantidad de dinero'}
>{nombre: 'Spiderman', poder: 'La mejor reaccion alergica a las picaduras de araña'}
```
Examinando el codigo anterior, podemos deducir que es antes del `await` es un simple `forOf`, que impriria promesas , no resultados de promesas, pero asignado el await despues del for, indica que tiene que resolver la promesa y luego imprimer el objeto pedido, siendo asi ,el proceso individual de cada promesa con la eficiencia que se necesitaba