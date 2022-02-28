# Propiedades , Gets , Metodos Estaticos

La opcion de volver estaticos algunos elemento sirven par no tener necesidad de crear una instancia.  
Propiedad Estatica  
Sintaxis:

```
static nameProperty;
```

Ejemplo:

```
static _conteo = 0;
```

Esta propiedad no sera visualizada en la creacion del objeto y esta pertenece a la clase, tomando le ejemplo del documento anterior, digamos que la propiedad estatica `_conteo`, tomara cuenta de los objetos creados por el generado de objetos (Clase), y para ello lo podremos en el constructor ya que este se activa cada vez que creamos un objeto.

```
...
constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        // console.log(`Hola!`)
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
        Persona._conteo++;
    }
....
```

De esta forma si decirmos que fueron creados 2 objetos a partir del generador de objetos(clase) la forma en que podemos visualizarla es la siguiente:

```
console.log(`Conteo Estatico ${Persona._conteo}`)
```

Como resultado:
`>Conteo Estatico 2`

Es decir es la propiedad de la clase, no de lo que genera la clase

# Get

Poniendo el ejemplo anterior , digamos que necesitamos le valor de la propiedad `_conteo` pero manipualdo ya sea mensaje u otra situcion , para ello creamos un get.  
Sintaxis:

```
static get getName(){
    //get body
    return
}
```

Ejemplo:

```
static get getConteo(){
    return Persona._conteo + 'Instancias'
}
```

Este get no sera visualizado en la creacion del objeto, y esta pertenece a la clase, de esta forma podemos llamarla de la siguiente forma:

```
console.log(Persona.getConteo)
```

Como resultado:  
`> 2 Instancias`

# Metodo Estatico

Tomando el ejemplo anterior, para el metodo las retricciones son que no puedes tomar las propiedades que si van a hacer tomadas por el generador de objetos(la clase), para ello imprimieremos un mensaje:

```
nameMethod(arguments){
    //body Method
}
```

Ejemplo

```
static mensaje() {
        console.log(this.nombre) //undefined
        console.log('Hola a todos, soy un metodo estatico')
    }
```

Para visualizar la restriccion antes mecionada colocaremos el `this.nombre`  
Mandamos a llamar el metodo
```
Persona.mensaje()
```
Dando como resultado  
`> undefined`  
`> Hola a todos, soy un metodo estatico`

Es decir , los metodos estaticos nos permiten manipular la clase misma, teniendo informacion que se puede manipular para la obtencion de la misma 