# Logica booleana

La logica booleana indica de cierta forma como trabaja javascript , dado que se rigue de condiciones en todo momento.

# NOT o la negacion

la forma en la cual puedes negar un resultado es con el simbolo **!**  
Ejemplo  
`console.log(true);` Como resultado da true  
`console.log(!true);` Como resultado da false, dado que estamos negando el mismo true  
`console.log(!false);` Asi como tambien se puede definir que se puede negar false

### Se puede hacer la negacion con cualquier valor booleano

# AND

El operador and **&&**  
dicta que todos lo valores deben ser true, para dar true , es decir que todos los valores u condiciones deben de dar verdadero , para que lo que se esta declarando de true.  
`console.log(true && true); // true` como resultado da true  
`console.log(true && false); // false` como resultado da false  
`console.log(true && !false); // true` como resultado da true

Si por ejemplo la primera condicion o valor a evaluar da false el programa ya no seguira evaluando los demas valores. Ejemplo:  
Declarando funciones:

```
const regresaTrue = () => {
  console.log("regresa true imbecil");
  return true;
};

const regresaFalse = () => {
  console.log("regresa False imbecil");
  return false;
};
```

Evaluando And:

```
console.log(regresaFalse() && regresaTrue());
```

Como resultado solo se imprime:

```
>regresa False imbecil
>false
```

Demostrando asi que no ejecutara el codigo restante

# OR

El operador or **||**
Dicta que un unico valor debe de dar true, para dar true, es decir que un solo valor u condicion deben de dar verdadero, para que lo que se este declarando de true.  
`console.log(true || false); //true` Como resultado da true  
`console.log(false || false); //false` Como resultado da false  
Si por ejemplo la primera condicion o valor a evaluar da true el programa yo no seguira evaluando los demas valores.Ejemplo:  
Declarando funciones:

```
const regresaTrue = () => {
  console.log("regresa true imbecil");
  return true;
};

const regresaFalse = () => {
  console.log("regresa False imbecil");
  return false;
};
```
Evaluando OR:
```
console.log(regresaTrue() || regresaFalse());
```
Como resultado solo se imprime:

```
>regresa true imbecil
>true
```
