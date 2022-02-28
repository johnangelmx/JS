# Funciones

## Funciones basicas y de flecha

Manera basica de invocar funciones seria:

```
function name(params) {

}
```

Ejemplificando:

```
function saludar() {
  console.log("Hola mundo");
}

saludar();
```

Otro tipo de manera de invocar una funcion seria con funcion anonima, porque no tiene nombre, pero asignandole una variable a una funcion corresponde a saludar2 :

```
const saludar2 = function() {
    console.log("Hola mundo");
  }
```
## Funciones de flecha 
```
const saludarFlecha = () => {
  console.log("Hola Flecha");
};
```
## Retorno de funciones 
Las funciones tienden normalmente a retornar un valor o ninguno , depende de la situacion , pero al devolver un valor de la misma se utiliza el   
`return`  
El return devuelve un valor, parametro , etc de la funcion que se invoco ,y se puede almacenar por medio de la variable.  
El return tiende a des-invocar la funcion , es decir toda linea de codigo que este despues del return , dentro de la funcion ya no sera leida.  
Una forma de retorna sin usar el `return`, seria: 
```
const sumar = (a, b) => a + b;
```
