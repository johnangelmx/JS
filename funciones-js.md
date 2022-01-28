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

Otro tipo de manera de invocar una funcion seria con funcion anonima, porque no tiene nombre, pero asignandole a una funcion corresponde a saludar2 :

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
