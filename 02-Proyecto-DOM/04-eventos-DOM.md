# Eventos 
Para poder manipular el documento HTML, desde codigo se necesita eventos que los accionen, es decir , si yo manipulo algo del documento HTML y quiero que este, haga una accion se tiene que ingresar codigo en JavaScript.  

Digamos que tenemos un boton a manipular,y este pide de un juego de cartas una carta, el boton tiene un elemento id , ejemplifiquemoslo:
```
<button id="btnPedir">Pedir Carta</button>
```
Para ello primero guardaremos la referencia del boton en una variable:
```
const btnPedir = document.querySelector('#btnPedir');
```
como resultado , la variable **btnPedir** almacena:
```
<button id="btnPedir">Pedir Carta</button>
```
# Creando accion
Para poder crear una accion , en este caso un **'Click'** en el boton Pedir carta, se utiliza el `.addEventListener()` .  

El Metodo `.addEventListener()`, lleva dos parametros, el primero seria la accion que se espera en este caso el **'click'**:  
`.addEventListener('click',)` , y el segundo parametro es la funcion al realizar dicho click , para ello invocamos una funcion de flecha (estandar):  
`.addEventListener('click', ()=>{ })`  
Esto recibe el nombre de **CALLBACK**, es decir, funcion que se esta mandando como argumento.

Cabe mencionar que el `.addEventListener()` como acciones a la misma no solo es el **'click'** , si no tambien existe el **'dbclick'** o **'focus'** , etc etc...  
Parte del codigo  y ejemplo a seguir:
```
btnPedir.addEventListener('click',()=>{
    console.log('click idiota')
})
```
El `console.log` añadido es para ejemplificar que pasaria si se click en el boton , teniendo como resultado en consola:
```
>'click idiota'
```