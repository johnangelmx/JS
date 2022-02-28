# Operador condicional ternario

**if else resumido**  
El operador ternario permite resumir de manera mas limpia un if-else , y asiganarlo a un varible , para que pueda ser utilizada de mejor manera y mas optimizada.  
La forma en la cual un operador puede ser utilizado es:  
`const nombreVariable = (condicion) ? siCumpleCondicion : siNoCumpleCondicion`  
De forma simplificada, seria:  
`const nombreVariable = (condicion) ? if : else`  

En el caso de necesitar mas de una condicion se realiza de la siguiente forma: 
```
const nombreVariable = (condicion) ? siCumpleCondicion :
                       (condicion2) ? siCumpleCondicion :
                       (condicion3) ? siCumpleCondicion :
                       (condicion4) ? siCumpleCondicion :
                       (condicion5) ? siCumpleCondicion :
                       (condicion6) ? siCumpleCondicion :
                       (condicion7) ? siCumpleCondicion : siNoCumpleCondicion;
```

# Pro-Tip
El operador ternario se puede utilizar para retornar funciones, Ejemplo:  
```
const elMayor = (a, b) => (a > b ? a : b);
``` 
Se Manda a llamar:  
```
console.log(elMayor(20, 15));
```
Como resultado da:
```
>20
```
Otro tipo de ejemplo:
```
const tieneMembresia = (miembro) => (miembro ? "2 Dolares" : "10 Dolares");
```
Se Manda a llamar:  
```
console.log(tieneMembresia(false));
```
Como resultado da:
```
> "10 Dolares"
```
Visualizando asi que se utilizar el operador ternario en funciones  
  
## En Arreglos
```
const amigo = false;
const amigosArr = [
  "Peter",
  "Tony",
  "Dr.Stange",
  amigo ? "Thor" : "Loki",
  // (() => 'Nick Fury')(), // Esto es una funcion autoinvocada
  elMayor(10, 15),
];
```
Cabe constatar que no solo en funciones y vaiables se puede calcula con el operador ternario , si no tambien dentro de arreglos como el ejemplo anterior ,JavaScript tiene la liberatad de porder hacer calculos de este tipo dentro de su lenguaje


