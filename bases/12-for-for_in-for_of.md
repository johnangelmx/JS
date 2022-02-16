# Ciclos For

## For

El ciclo for tiene como estandar lo siguiente:

```
for (let i = 0; i < array.length; i++) {


}
```

> Dado que implica que el primer argumento `let i = 0;` , es la inicializacion de la misma.  
> El segundo argumento `i < array.length` es la condicion a evaluar para iniciar/continuar el ciclo.  
> Y el tercer argumento `i++` , es el contador la forma que en cada ciclo el primer argumento va a aumentar.

Ejemplo:  
Crearmos un arreglo a barrer , es decir a imprimir cada elemento del mismo, en cada vuelta del ciclo

```
const heroes = ["Batman", "Supermans", "Mujer Maravilla", "Aquaman"];
```

Creamos el for estandar:

```
for (let i = 0; i < heroes.length; i++) {
  console.log(heroes[i]);
}
```

Y como resultado obtenemos:

```
>Batman
>Supermans
>Mujer Maravilla
>Aquaman
```

Para plasmar la idea mas clara , a su vez como se ve en los anteriores ciclos e if-else, la condicion a evaluar es la misma, **la condicion a evaluar siempre sera un true o un false**, y ejemplificando lo anterior al tener la variable `i` en la posicion 4 , la condicon dictaria `4 < 4` cuatro es menor que cuatro, siendo la respuesta no , son iguales a los que dicta como un false saliendo del ciclo , esto para dejar claro que las condicion en JavaScript son con las bases true o false.

# For In

Una forma mas facil para **"Barrer"** un arreglo seria con for in teniendo como estandar:

```
for (const key in object) {

}
```

> Dado que implica el primer elemento la variable que tomara el valor en cada ciclo `const key`.  
> El segundo elemento es el estandar `in`  
> Y el tercer elemento es objeto/ arreglo a evaluar/ barrer

Ejemplo:  
Crearmos un arreglo a barrer , es decir a imprimir cada elemento del mismo, en cada vuelta del ciclo

```
const heroes = ["Batman", "Supermans", "Mujer Maravilla", "Aquaman"];
```

Creamos el for in:

```
for (let i in heroes) {
  console.log(heroes[i]);
}
```

Y como resultado obtenemos:

```
>Batman
>Supermans
>Mujer Maravilla
>Aquaman
```

Para entender de forma mas simplificadad, con el **for in** no necesitamos un contador que vaya teniendo la cuenta de cada vuelta como en el **for estandar**.

En este caso la variable creada sirve como contador de cada vuelta que da el ciclo, tomando asi cada elemento del arreglo como variable reutilizable dentro de las **{ }** del **for in**, y despues del `in` el objeto a evaluar en este caso un arrreglo toma como referencia cuantos valores tiene ,y esos mismos el numero de vuelta que dara.

# For of

Una forma de **"Barrer"** mas facil y reutilizando los valores de forma mas eficiente es con el **for of**, teniendo como forma estandar:

```
for (const iterator of object) {

}
```

> Dado el primer argumento `const iterator` este indica el valor que tomara en cada vuelta del ciclo.  
> El segundo elemento es el estandar `of`  
> Y el tercer elemento es objeto/ arreglo a evaluar/ barrer
> Ejemplo:  
> Crearmos un arreglo a barrer , es decir a imprimir cada elemento del mismo, en cada vuelta del ciclo

```
const heroes = ["Batman", "Supermans", "Mujer Maravilla", "Aquaman"];
```

Creamos el for of:

```
for (let heroe of heroes) {
  console.log(heroe);
}
```

Y como resultado obtenemos:

```
>Batman
>Supermans
>Mujer Maravilla
>Aquaman
```

Para entender de forma mas simplificada, con **for of** no necesitamos como en el **for in** , tomar la variable creada como numero/posicion-arreglo para poder disponer de ella, sino unicamente nombrandola como fue declara en la inicializacion del **for of**.  

Normalmente como estandar se utiliza el singular del nombre de arreglo/objeto como variable creada del primer argumento.  

En este caso la variable creada sirve para reutilizar dentro del for y darle alguna instruccion, tomando asi cada elemento del arreglo como variable reutilizable dentro de las **{ }** del **for of**, y despues del `of` el objeto a evaluar en este caso un arrreglo toma como referencia cuantos valores tiene ,y esos mismos el numero de vuelta que dara.
