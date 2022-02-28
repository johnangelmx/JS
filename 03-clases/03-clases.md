# Clases

Como vimos en el apartado anterior , podemos decir que las clases, son un creador objetos ,objetos que claramente cumplan con las propiedades que necesitaremos establecer en todos ellos de una misma clase, es decir, objetos que tienen las mismas propiedades ah asignar.  
Para ello utilizamos la siguiente sintaxis estándar de las clases:

```
class [className]{
  // class body
  constructor(arguments){
  }
};
```

la cual empezaremos a plantearla con el siguiente interrogante; Crearemos una clase que tenga el nombre persona, y almacenara 3 propiedades que seran nombre,clave y frase:

```
class Persona {
    constructor(){}
}
```

Las clases van con OperCamelCases, es decir, mayúsculas a inicio de cada palabra, esto de forma estandarizada para un buen manejo de código.  
El constructor es un metodo que se ejecutara al mismo tiempo que estemos ejecutando la clase, ejemplifiquemos:

```
class Persona {
    constructor(){
        console.log('Hola! soy el metodo')
    }
}
```

Para crear un nuevo objeto del generador de objetos (Clase), lo almacenaremos en una variable y con la palabra reservada `new` crearemos una nueva instancia de ello:

```
const spiderman = new Persona ()
```

Teniendo como resultado:  
`>Hola! soy el metodo`  
Demostrando asi que el método se ejecuta al mismo tiempo que la clase.

## Estableciendo las propiedades

Ahora bien para poder establecer las clases que se utilizaran en este caso: nombre,clave y frase, tendremos que establecerlas al principio de la clase y después del constructor:

```
class Persona {
   nombre;
   clave;
   frase;
   constructor(){
       console.log('Hola! soy el metodo')
   }
}
const spiderman = new Persona ()
```

e inicializamos para no tener problemas de undefined:

```
class Persona {
   nombre = '';
   clave = '';
   frase = '';
   constructor(){
       console.log('Hola! soy el metodo')
   }
}
const spiderman = new Persona ()
```

¿Ahora como podremos utilizar una variable dentro de la misma clase?
Tendremos que utilizar el ejemplo del documento anterior para establecer que en este caso también podremos utilizar el `this` porque de lo contrario no podríamos utilizar una variable que esta definida dentro de la misma clase, Ejemplifiquemos:

```
class Persona {
   nombre = '';
   clave = '';
   frase = '';
   constructor(){
       console.log('Hola! soy el metodo')
       clave = 'ABC'
   }
}
const spiderman = new Persona ()
```

Aqui asiganremos un valor a la propiedad clase, teniendo el siguiente mensaje  
`>Uncaught ReferenceError: ABC is not defined at new Persona `

Teniendo asi el problema dicho anteriormente que no podemos acceder a la variable dentro de la misma clase o funcion, para ello utilizaremos el `this`

```
class Persona {
   nombre = '';
   clave = '';
   frase = '';
   constructor(){
       console.log('Hola! soy el metodo')
       this.clave = 'ABC'
   }
}
const spiderman = new Persona ()
```

Teniendo como resultado:  
`>Persona {nombre: '', codigo: 'abc', frase: ''}`  
Asi que para poder asignar lo como propiedades lo que nos envien para instanciar el nuevo objeto es decir los parametros que recibimos en:
`const spiderman = new Persona ()` , tendremos que primero que nada establecerlos en el constructor con su debida instruccion por defecto es decir si no recibimos un parametro , lo asigaremos de otra forma:

```
class Persona {
    nombre = ''
    codigo = ''
    frase = ''
    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {

    }
}
```

Y despues asignando los parametros que recibimos en las propiedades asignadas:

```
class Persona {
    nombre = ''
    codigo = ''
    frase = ''
    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
    }
}
```

Teniendo asi el siguiente resultado al almacenarlo e imprimirlo:

```
const spiderman = new Persona('Peter Parker', 'SpiderMan', 'Soy tu amigable vecino Spideman')

console.log(spiderman)
```

Resultado:  
`Persona {nombre: 'Peter Parker', codigo: 'SpiderMan', frase: 'Soy tu amigable vecino Spideman'}`

Creando otro objeto:

```
const ironman = new Persona('Tony Stark', 'Iron Man ', 'Yo soy Ironman puta')
```

Resultado:  
`Persona {nombre: 'Tony Stark', codigo: 'Iron Man ', frase: 'Yo soy Ironman puta'}`
