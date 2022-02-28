# Estructura de control
Ejecuta una sentencia si una condición específicada es evaluada como verdadera. Si la condición es evaluada como falsa, otra sentencia puede ser ejecutada.
```
if (condition) {
    
}
```

## Apartado codigo limpio
```
// Sin usar if else , o swtich, unicamente objetos y arreglos
dia = 1;

let semana = ['Domingo','Lunes','Martes','Miercoles','Jueves','Viernes','Sabado'];

console.log(semana[dia]);

let semanaDias = {
  0:"Domingo",
  1:"Lunes",
  2:"Martes",
  3:"Miercoles",
  4:"Jueves",
  5:"Viernes",
  6:"Sabado"
}
console.log(semanaDias[dia] || 'Dia no valido');
```` 
## Una forma de ejecutar funciones por medio de arreglos u objetos
```
dia = 1;
let semanaDias = {
  0: ()=> "Domingo - 0",
  1: ()=> "Lunes - 1",
  2: ()=> "Martes - 2",
  3: ()=> "Miercoles - 3",
  4: ()=> "Jueves - 4",
  5: ()=> "Viernes - 5",
  6: ()=> "Sabado - 6",
}
console.log(semanaDias[dia]());
```