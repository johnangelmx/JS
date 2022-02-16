# Valor por referencia

En JavaScript, cuando asignamos un valor a una variable, o pasamos un argumento a una función, este proceso siempre se hace “por valor” (by value en inglés). Estrictamente hablando, JavaScript no nos ofrece la opción de pasar o asignar “por referencia” (by reference en inglés), como en otros lenguajes. Lo interesante en nuestro caso, es que cuando una variable hace referencia a un objeto (Object, Array o Function), el “valor” es la referencia en sí.

Cuando asignamos valores primitivos (Boolean, Null, Undefined, Number, String y Symbol), el valor asignado es una copia del valor que estamos asignando. Pero cuando asignamos valores NO primitivos o complejos (Object, Array y Function), JavaScript copia “la referencia”, lo que implica que no se copia el valor en sí, si no una referencia a través de la cual accedemos al valor original.

En pocas palabras JavaScript toma los "valores por referencia" de forma tal que modificas el mismo valor por si mismo.  
Y si lo haces "por valor", si hace una copia de este sin modificar el original.  
Ejemplo:

```
let a = 10;
let b = a;
a = 30;
```

Lo imprimimos

```
console.log({ a, b });
```

Y el valor seria :

```
{a: 30, b: 10}
```

## Desmostrando por referencia:

Ejemplo:

```
let juan = { nombre: "Juan" };
let ana = juan;
ana.nombre = "ana";
```

Lo imprimimos

```
console.log({ juan, ana });
```

Y el valor seria:

```
˅{juan: {…}, ana: {…}}
  >ana: {nombre: 'ana'}
  >juan: {nombre: 'ana'}
```

Tomando en cuenta lo que se explicó , el valor de ana, se modifico en ambos casos, demostrando que JavaScript pasa a (Object, Array o Function) valores por referencia, es decir modificando el valor original cada que se manda a llamar a los mismos.

Como podriamos convertir dichos valores de referencia a valor?

# Operador SPREAD

El operador SPREAD permite crear dicha copia a valores pasados por referencia haciendo asi la mejor manipulacion de codigo y utilizacion de la misma.  
Tomando el ejemplo anterior  
**Como podriamos convertir dichos valores de referencia a valor?**

```
let juan = { nombre: "Juan" };
let ana = juan;
ana.nombre = "ana";
```

En el ejemplo anterior tendriamos este codigo, que pasa por referencia, para poder hacer una copia de ello ,y pasar por valor , en este caso que ana tenga una copia de juan que pueda manipular se utiliza el operador SPREAD **Que consiste en encerrar el valor de la variable en su misma declaracion e ingresar 3 puntos antes de la declaracion**  
Es decir, en el caso anterior juan es un objeto { } y para ello se utiliza llaves , depues se integra los 3 puntos quedadando como resultado.

```
let ana = {...juan};
```

de esta forma se hace una copia de la misma y no pasa por referencia si no por valor, siendo una copia de juan:

```
let juan = { nombre: "Juan" };
let ana = { ...juan };
ana.nombre = "ana";
```

Lo imprimimos

```
console.log({ juan, ana });
```

```
˅{juan: {…}, ana: {…}}
  >ana: {nombre: 'ana'}
  >juan: {nombre: 'Juan'}
```

# SPREAD en arreglos

```
const frutas = ["Manzana", "Pera", "Piña"];
const otraFrutas = frutas;
otraFrutas.push("Mango");
```

Imprimiendo:

```
console.table([frutas,otraFrutas]);
```

Y el resultado seria:

```
┌─────────┬───────────┬────────┬────────┬─────────┐ 
│ (index) │     0     │   1    │   2    │    3    │ 
├─────────┼───────────┼────────┼────────┼─────────┤ 
│    0    │ 'Manzana' │ 'Pera' │ 'Piña' │ 'Mango' │ 
│    1    │ 'Manzana' │ 'Pera' │ 'Piña' │ 'Mango' │ 
└─────────┴───────────┴────────┴────────┴─────────┘ 
```

## Con el operador SPREAD:

```
const frutas = ["Manzana", "Pera", "Piña"];
const otraFrutas = [...frutas];
otraFrutas.push("Mango");
```

Imprimiendo:

```
console.table([frutas,otraFrutas]);
```

Y el resultado seria:

```
┌─────────┬───────────┬────────┬────────┬─────────┐ 
│ (index) │     0     │   1    │   2    │    3    │ 
├─────────┼───────────┼────────┼────────┼─────────┤ 
│    0    │ 'Manzana' │ 'Pera' │ 'Piña' │         │ 
│    1    │ 'Manzana' │ 'Pera' │ 'Piña' │ 'Mango' │ 
└─────────┴───────────┴────────┴────────┴─────────┘ 

```
# SPREAD funciones y objetos
```
const cambiaNombre = (persona) => {
  persona.nombre = "Tony";
  return persona;
};
```
```
let peter = { nombre: "Peter" };
let tony = cambiaNombre(peter);
```
Imprimiendo:
```
console.log({ peter, tony });
```
Resultado:
```
{ peter: { nombre: 'Tony' }, tony: { nombre: 'Tony' } }
```
## Con el operador SPREAD:
```
const cambiaNombre = ({ ...persona }) => {
  persona.nombre = "Tony";
  return persona;
};
```
```
let peter = { nombre: "Peter" };
let tony = cambiaNombre(peter);
```
Imprimiendo:
```
console.log({ peter, tony });
```
Resultado:
```
{ peter: { nombre: 'Peter' }, tony: { nombre: 'Tony' } }
```
Demostrando asi , la utilidad del spread como copia de un valor que pasa por referencia
