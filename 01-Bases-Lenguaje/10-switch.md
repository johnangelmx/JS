# Switch
La sentencia de control switch , dicta que puedes utilizar en varios casos una condicion,es decir tienes un if con multiples condiciones , la estrutura principal se necesita lo siguiente:

```
switch (key) {
    case value:
        
        break;

    default:
        break;
}
```
Ejemplo: 
```
const dia = 0; // 0:domingo
```
Evaluando con switch: 
```
switch (dia) {
    case 0:
        console.log('Domingo');
        break;
    case 1:
        console.log('Lunes');
        break;
    case 2:
        console.log('Martes');
        break;
    default:
        console.log('No es lunes, Martes o Domingo');
        break;
}
```
Como se denota puedes ver que puedes condicionar varios casos en los cuales, podria hacerce de forma mas facil como ejemplos anteriores, pero en este caso sirve para reflejar el ejemplo de los casos.  
Los Cuales siempre deben de tener un break, el cual sirve para salir del switch una vez que se haya cumplido el caso a evaluar.  
El default sirve para evaluar un caso en el cual no esta evaluando , es decir una excepcion.
