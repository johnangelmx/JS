# Ciclos

La sentencia de control while, dicta que si la condicion a evaluar es true, el ciclo continuara ejecutandose de lo contrario no sera tomada en cuenta.  
Ejemplo de la estructura
While:

```
while (condition) {

}
```

Ejemplificandolo:

```
const carros = ["Ford", "Mazda", "Honda", "Toyota"];
let i = 0;
```

Invocando la funcion while

```
while (i < carros.length) {
    console.log(carros[i]);
    i++;
}
```

como resultado:

```
>"Ford"
>"Mazda"
>"Honda"
>"Toyota"
```

Esto demostrando que el ciclo comienza en 0 y hace la siguiente verficacion:  
 0 es menor que carros.length `(0 < 4)`, siendo un true, un verdadero a la condicion a evaluar, a lo consiguiente imprimiendo la posicion 0 del arreglo de carros `"Ford"`, y como siguiente aunmentando en uno la variable i, `i++;`, asi hasta llegar a la posicion 4:  
 `(4 < 4)` 4 es menor que carros.length ?, la respuesta es un false, 4 es igual a 4, asi terminando el ciclo .

# Persepcion de valores

Como se vio en el apartado de asignacion con operadores, al tener valor una variable, se detecta como true, y unicamente al tener un `undefined,null,false` dentro de dicha variable a evaluar, lo dectecta como falso.  
 Es decir se puede tomar como condicion si un valor se encuentra true o false.  
 Tomando el ejemplo anterior:

```
while (carros[i]) {
 console.log(carros[i]);
 i++;
}
```
Tomemoslo de la siguiente manera , al tener un valor en la posicion 0 , en este caso un valor string siendo `"Ford"`, la condicion puede ser aceptada siendo true , y entrando en el ciclo while.  
Asi llegando a la posicion 4, que el valor de dicha posicion da `undefined`, la condicion siendo rechazada dando un false
# Do While
La sentencia de control Do while a diferencia del while , este si ejecuta por lo menos una vez el contenido dentro de ella, es decir no evalua la condicion a repetir sino hasta el final del ciclo. Siendo asi la ejecucion unica si la condicion true  
Ejemplo:
```
let j = 0;
do {
  console.log(carros[j]);
  j++;
} while (carros[j]);

```
Resultado:
```
>"Ford"
>"Mazda"
>"Honda"
>"Toyota"
```
Pero que pasa si definimos un valor que no esta en el arreglo?
```
let j = 10;
do {
  console.log(carros[j]);
  j++;
} while (carros[j]);
```
Resultado
```
undefined
``` 
Como se puede ver la posicion no existe dando como resultado un `undefined`, asi de la misma manera evalua al final si el valor de carros en la posicion 10 ,contiene un valor y que este sea true unicamente si no contiene `undefined,null,false`, en este caso al ser `undefined` marca como false, y asi no ejecutando el ciclo do-while.