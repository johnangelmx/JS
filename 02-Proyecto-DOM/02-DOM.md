# DOM - Document Objet Model

Conjunto de objetos aninados, para crear un elemento html , acesso dinamico atravez de programacion a sus elementos.

### Acceso dinamico

El modelo de objeto de documento (DOM) es una interfaz de programación para los documentos HTML y XML. Facilita una representación estructurada del documento y define de qué manera los programas pueden acceder, al fin de modificar, tanto su estructura, estilo y contenido. El DOM da una representación del documento como un grupo de nodos y objetos estructurados que tienen propiedades y métodos. Esencialmente, conecta las páginas web a scripts o lenguajes de programación.

# Tipos de datos importantes

Esta parte intenta describir, de la manera más simple posible, los diferentes objetos y tipos. Pero hay que conocer una cantidad de tipos de datos diferentes que son utilizados por el API. Para simplificarlo, los ejemplos de sintaxis en esta API se refieren a nodos como elements, a una lista de nodos como nodeLists (o simples elementos) y a nodos de atributo como attributes.

Lo siguiente describe brevemente estos tipos de datos.

**document** Cuando un miembro devuelve un objeto del tipo document (por ejemplo, la propiedad ownerDocument de un elemento devuelve el documento "document" al cual pertenece), este objeto es la raíz del objeto documento en sí mismo.

# Recomendacion estandar

Para la mejor optimizacion de manipulacion del DOM , se recomienda usar el `.querySelector()` y el `.querySelectorAll()`.  
El `.querySelector()` es la forma en la cual podemos tomar un elemento , ya sea etiqueta , clase u id dentro de nuestro "documento html" , el `.querySelector()` toma el primer elemento del documento, SOLO EL PRIMER ELEMENTO, para manipular dichos elementos de mayores cantidades tenemos:
El `.querySelectorAll()` toma todos las etiquetas, clases u Id's dentro del documento , y estos convirtiendolos en un arreglo llamado "NodeList".

**nodeList** Una "nodeList" es una serie de elementos, parecido a lo que devuelve el método document.getElementsByTagName(). Se accede a los items de la nodeList de cualquiera de las siguientes dos formas:
list.item (1)
lista [1]
Ambas maneras son equivalentes. En la primera, item() es el método del objeto nodeList. En la última se utiliza la típica sintaxis de acceso a listas para llegar al segundo ítem de la lista.

# Ejemplos

Tomando como referencia el siguiente documento html

```
<html>
 <head>
    <title>BlackJack</title>
 </head>
 <body>
    <header class="titulo" id="titulo">Blackjack</header>
 </body>
</hmtl>
```
Para poder manipular el header, el titulo en nuestro documento utilizamos de primera instancia la etiqueta
```
document.querySelector('header')
```
Y para poder manipular el tendo dentro de las etiquetas , como si fuera estuvieramos manipulando un objeto llamamos al metodo **.innerText** asignadole el valor del string a utilizar:
```
document.querySelector('header').innerText = 'Nuevo titulo';
```
Para poder manipularlo desde la clase:
```
document.querySelector('.titulo').innerText = 'Nuevo titulo';
```
Para poder manipularlo desde el id:
```
document.querySelector('#titulo').innerText = 'Nuevo titulo';
```
Para poder insertar una instruccion HTML usamos el **.innerHTML**, el cual nos permitira ingresar codigo HTML al documento y no solo un valor string al mismo .
```
document.querySelector('header').innerHTML = '<h1>Nuevo titulo</h1>';
```
# Creacion de elementos HTML
Parte de la creacion de elementos es poder tener la minipulacion sin escribir muchas veces el document.etc...  
para ello es recomendable guardar esa referencia en una variable: 
Tomando como referencia el siguiente documento html

```
<html>
 <head>
    <title>BlackJack</title>
 </head>
 <body>
    <header class="titulo" id="titulo">Blackjack</header>
    <div id="divBotones">
        <button>Play</button>
    </div>
 </body>
</hmtl>
```
Para poder almacenar una referencia de una instruccion DOM , tendremos que almacenarla en una varible para ello hacemos lo siguiente:
```
const divBotones = document.querySelector('#divBotones');
```
con ello ya tendremos un elemento creado que hace referencia a ese **div**
## Crear un nuevo elemento
Para ello utilizaremos el **`.createElement()`**, que este recibira una etiqueta a ingresar.  
Como se habia visto en partes anteriores JavaScript se maneja por referencia asi que para poder ingresar un nuevo elemento en este caso un **BOTON** vamos a necesitar almacenar ese **BOTON** en una varible 
```
const botonNuevo = document.createElement('button');
```
Y como resultado dentro de la varible tendremos: 
```
<button></button>
```
Como mencione , se maneja por referencia , asi que las modificaciones que hagamos dentro del **botonNuevo** , seran las que se almacene en la misma.
## Adheriendo ambos elementos
Ahora para insertar el **botonNuevo** dentro de el div que almacenamos en **divBotones** se utiliza la instruccion **`.append()`**:
```
divBotones.append(botonNuevo);
```
Teniendo asi un boton en el div que queriamos insertalo.
Ahora bien para añadirle un texto , tanto como pasa como referencia, solo se necesita insertarlo en **botonNuevo**:
```
botonNuevo.innerText = 'Hola mundo' 
```
Para ingresar una clase dentro de la etiqueta utilizamos el `.classList` junto con el `add()`:
```
botonNuevo.classList.add('btn')
```
Para ingresar un ID dentro de la etiqueta utilizamos el `.id` y como si fuera el `.innerText` lo declaramos con un **igual(=)** : 
```
botonNuevo.id = 'soyUnId';
```
# Ejemplo adheriendo un input al final del body
iniciamos guardando el elemento en una variable
```
const input = document.createElement('input');
```
y para adherirlo o incluirlo al final del body:
```
document.querySelector('body').append(input);
```
Para insertar un placeholder al input:
```
input.placeholder = 'hola mundo'
```
