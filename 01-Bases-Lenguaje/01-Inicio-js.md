# Guia Javascript

Hola mundo , y visualizacion en consola: <br>
`console.log('Hola mundo');` <br>
Hola mundo , y visualizacion en el navegador: <br>
`document.write('Hola mundo');` <br>
<br>
Nota: el primer comando por consola funciona de la misma manera en node.js

# Variable y comentarios

Comentarios: `// ` <br>
Variable, es un contenedor de informacion que apunta a un lugar en memoria. Dicha informacion puede cambiar en el futuro. <br>
Tipos de variables: <br>
`let ` La variable let es la mas recomendada hoy en dia dado que se ha convertido en un standar del lenguaje, es una variable que cambia conforme la utilizas. <br>
`var ` La variable var es la menos recomendada dado que que cierta forma esta variable puede cambiar palabras reservedas en alto nivel , es decir no tiene restriccion alguna antes al creacion y manipulacion de variable ya establecidas por el codigo o por el lenguaje <br>
`const` la variable const , sirve para declarar un valor que no puede ser modificado en un futuro , el valor es inmodificable <br>

# Tipo de console

`console.log( ) ` Es una forma estadar de ver la informacion en el navegador<br>
`console.warn( ) `La visualizacion estara en amarrillo con su respectivo icono de advertencia <br>
`console.error( ) `La visualizacion estara en rojo con su respectivo icono de Peligro o error<br>
`console.info( ) ` Visualiza de mejor manera el contenido declarado<br>
`console.table() ` Visualiza de manera grafica una tabla, con el contenido declarado<br>

# Consejos con el console

Una de las mejores formas y mas reconmendables de visualizar contendo detallado de los console's ya sea variable, cadenas , etc. Es agragando { } llaves al contenido declarado en el console: <br>
`console.log({})` <br>
Este serviria para visualizar el nombre de la variable, cadena, u objeto desde que se declara, todo para ahorro de escritura.<br> <br>
Una forma de agregar estilos a los console dentro del navegador seria de la siguiente forma : <br>
`console.log('%c Mis variables' , 'color: white; font-weight:bold');`
<br>

# Orden y consejos de ubicaciones

Parte de las buenas practicas es crear carpeta de recursos: <br>
`assets/` <br>
la importancia de crear este tipo de carpetas conforme el nombre es para que en frameworks futuros esto se indica como forma estandarizada y dentro de ingresar las mismas carpetas a utilizar ya sea <br> `css/` <br> `js/` <br> `sass/` <br> Etcetera

# prompt, confirm y alert

3 Tipos de forma de ingreso de informacion de usuario <br>
La primera de ellas es el: <br>
`alert('Hola mundo')` <br>
El alert es un mensaje flotante que detiene la ejecucion de la pagina hasta que aceptes el mensaje dentro de el.<br><br>
El segundo de ellos es el: <br>
`prompt('Cual es tu nombre? ', 'Sin nombre')`
El prompt consta de una caja en el cual puedes recibir un valor y almacenarlo en una variable, consta de 2 parametros mensaje y valor por defecto , ya sea en el caso del receptor un valor por defecto como el 'Sin nombre' o espacio en blanco <br>
Para almacenar dicho resultado del valor escrito en la caja de texto , se almacena de la siguiente manera: <br>
` let nombre = prompt("Cual es tu nombre? ", "Sin nombre");` <br><br>
El tercero de ellos es el: <br>
`confirm('Esta seguro de borrar esto?')`
El confirm consta de un mensaje y botones de aceptar y cancelar , dado el ejemplo de prompt, este es almacenable en una variable , pero solo regresa valores booleanos (true, false), true aceptando el mensaje y false cancelando el mensaje , estos a su vez pueden guardarse de la manera siguiente: <br>
`const seleccion = confirm('Esta seguro de borrar esto?')` <br><br>
Nota:Los 3 tipos de ingreso , son metodos del objeto window (objeto del leguaje de programacion javascript) <br>

# Tipo de dato de una variable

Describle el contenido del valor que tiene la variable

## Primitivos

Es una informacion que no es un objeto y son inmutables <br>

> Boolean - true / false :: Verdadero y falso <br>
> Null - Sin valor en lo absoluto <br>
> Undefined - Una variable declarada que aun no se le asigna valor <br>
> Number - integers, floats, etc. <br>
> String - Una cedena de carateres, ej: Palabras, nombres de personas<br>
> Symbol - Es un valor unico que no es igual a ningun otro valor <br>

Parte del dia a dia es la forma de saber que tipo de dato es una variable , pero cuando no tengamos alguna referencia a ello podemos utilizar el: type of <br>
`console.log(typeof nombre);` <br>
Consta de la palabra reservada y la variable a evaluar <br>

# Palabras reservadas y nombre de variables

Son palabras que tienen un uso especifico. <br>
No utilizar nombres de variables que lleven caracteres especiales.