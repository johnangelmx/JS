# Metodos

Un metodo es una función la cual es propiedad de un Objeto.  
Es decir un metodo es una funcion que pero creada de una forma mas simplificada en un objeto, como hablabamos en documentos atras las funciones pueden ser creadas de forma arcaica en un metodo , ejeplo simple:

```
const heroe = {
    nombre: 'Ironman',
    imprimirNombre: () => console.log(heroe.nombre)
}
heroe.imprimirNombre()
```

Tendremos como resultado:  
`> Ironman`

Para poder replicar esto en un geneador de objetos(clase), existen los metodos, los cuales dan mayores utilizades y de forma mas simplificada, usando el ejemplo del documento anterior:

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

const spiderman = new Persona('Peter Parker', 'SpiderMan', 'Soy tu amigable vecino Spideman')
```

Para poder insertar el metodo la sixtasis basica es:

```
nameMethod(arguments){
    //body Method
}
```

Asi que ingresemos un metodo que imprima el nombre y el codigo, de forma cual diga quien es y cual es su identidad:

```
quienSoy(){
    console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
}
```

y dentro de la clase seria:

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
    quienSoy(){
    console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
}
}

const spiderman = new Persona('Peter Parker', 'SpiderMan', 'Soy tu amigable vecino Spideman')
```
y para poder ingresar al metodo, como se hizo con primer ejemplo es:
```
spiderman.quienSoy();
```
como resultado:  
`> Soy Peter Parker y mi identidad es SpiderMan`  
Teniendo en cuenta en todo momento el uso de **( )** para llamar ese metodo, tal cual como las funciones,
Ahora intentemos con iron man:
```
const ironman = new Persona('Tony Stark', 'Iron Man ', 'Yo soy Ironman puta')

ironman.quienSoy()
```
Como resultado:  
`> Soy Tony Stark y mi identidad es Iron Man `  

Y como ultimo dato los metodos pueden funcionar dentro de otros metodos, pero teniendo en mente lo que hemos dicho en todo momento para poder utilizarlo dentro del mismo espacio de codigo , en este caso una clase debemos utilizar el `this`: ,teniedo el siguiente resultado:
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
    quienSoy(){
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
	        }
    miFrase() {
        this.quienSoy()
        console.log(`${this.codigo} dice: ${this.frase}`)
    }
}
```
y recordando las **( )** para poder invocar el metodo , tal cual se hace una funcion