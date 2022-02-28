# Funciones a utilizar

En Javascript hay funciones que pueden facilitar el codigo, en el apartado de bases/arreglos, tomamos algunas funciones que vimos utiles en arreglos, ahora veremos algunos utiles en strings

## substring
El substring() método devuelve un subconjunto de un objeto String.
```
cadena.substring(indiceA[, indiceB'])
``` 
substring extrae caracteres desde indiceA hasta indiceB sin incluirlo. En particular:

>Si indiceA es igual a indiceB, substring devuelve una cadena vacía.  
>Si se omite el indiceB, substring extrae caracteres hasta el final de la cadena.  
>Si el argumento es menor que 0 o es NaN, se trata como si fuese 0.  
>Si el argumento es mayor que nombreCadena.length, se trata como si fuese   nombreCadena.length.

De manera simplificada el metodo subtring toma dos valores en los cuales el primer valor dicta de donde inicia la extraccion dado que si fuese un arreglo ,y el segundo valor es donde terminara de extraer tomando en cuenta que este ultimo, no se extraera , no se tomara en cuenta.
Ejemplo:
```
// asume una función print ya definida
var cualquierCadena = "Mozilla";

// Muestra "Moz"
print(cualquierCadena.substring(0,3));
print(cualquierCadena.substring(3,0));

// Muestra "lla"
print(cualquierCadena.substring(4,7));
print(cualquierCadena.substring(7,4));

// Muestra "Mozill"
print(cualquierCadena.substring(0,6));
print(cualquierCadena.substring(6,0));

// Muestra "Mozilla"
print(cualquierCadena.substring(0,7));
print(cualquierCadena.substring(0,10));

```
## isNaN
La función isNaN() determina cuando el valor es NaN (La propiedad global NaN es un valor que representa Not-A-Number.) o no.

De manera simplificada, la funcion evalua si no es un numero, este devolvera true. Y si es un numero este devolvera false.
```
isNaN(NaN) //devuelve true
isNaN("string") //devuelve true
isNaN("12") //devuelve false
isNaN(12) //devuelve false
```