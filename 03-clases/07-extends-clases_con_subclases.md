# Extends - Clases Con Subclases

Supongamos que tengamos que hacer una clase, como el ejemplo anterior pero aderiendole clan en las propiedades, tendriamos que hacer otra clase y escribir todo?  
Ejemplicando:

```
class Persona {
    static _conteo = 0;
    static get conteo() {
        return Persona._conteo + ' instancias'
    }
    static mensaje() {
        console.log(this.nombre) //undefined
        console.log('Hola a todos, soy un metodo estatico')
    }
    nombre = ''
    codigo = ''
    frase = ''
    comida = ''

    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
        Persona._conteo++;
    }
    set setComidaFavorita(comida) {
        this.comida = comida.toUpperCase()
    }
    get getComidaFavorita() {
        return `la comida favorita de ${this.nombre} es ${this.comida}`
    }
    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
    }
    miFrase() {
        this.quienSoy()
        console.log(`${this.codigo} dice: ${this.frase}`)
    }
}
```

Tenemos esta clase del ejemplo anterior, y decirta forma necesitamos una nueva clase que tenga los mismos metodos y propiedades , pero en el apartado de propiedades tendremos que ingresar una mas, con el nombre de clan, claramente no tendremos que ingresar todo nuevamente.

En Javascript existe la forma de crear una clase con todos los metodos y propiedades de otra clase, ah esta metodologia se le llama padre e hijo, donde padre es alque copiaremos y el hijo es en el que podremos manipular sin necesidad de copiar todo.

Ejemplo:

```
class Heroe extends Persona {
    clan = 'No clan';
}
```

inicializaremos la clase de forma normal, pero para poder copiar los metodos y propiedades del padre, de cierta forma "extenderemos" la clase, para ello usaremos la palabra reservada `extends` y el nombre de la clase a reutilizar `Persona`.

Para ello imprimiremos el resultado, pero ahora resaltando que la creacion es con el nombre de la nueva clase `Heroe`:

```
const spiderman = new Heroe()
```

Como resultado:  
`> Heroe {nombre: 'sin nombre', codigo: 'sin codigo', frase: 'sin frase', comida: '', clan: 'No clan'}`

Como se puede ver los metodos y propiedades se heredaron de la clase `Persona`, incluyendo el nuevo parametro `clan`.  
Sin embargo no podemos manipularlo , ya que hace falta el constructor.

### super

La palabra reservada super sirve para poder usar el constructor con sus debidos metodos y parametros hereadados, de lo contrario no podremos manipular la clase "hijo".  
Ejemplo:

```
class Heroe extends Persona {
    clan = 'No clan';
    constructor(nombre, codigo, frase) {
        super();

    }
}
```

El codigo esta de la siguiente manera , clan esta inicializado en 'No clan', el constructor esta obteniendo los argumentos de nombre,codigo y frase ,pero no el de clan, y super esta establecido , pero el resultado es:  
Creamos el objeto y lo imprimimos

```
const spiderman = new Heroe('Peter Parker', 'SpiderMan', 'Soy tu amigable vecino Spideman')
console.log(spiderman)
```

nuevamente haciendo la observacion que se esta creando con la clase **Heroe**

`Heroe {nombre: 'sin nombre', codigo: 'sin codigo', frase: 'sin frase', comida: '', clan: 'No clan'}`

Como podemos ver aunque ya tengamos todo establecido, aun no visualizamos las propiedades, y es que es el `super` tambien es necesario los argumentos a utilizar de la clase anterior.  
Ingresaremos los argumentos y estableceremos el clan

```
class Heroe extends Persona {
    clan = 'No clan';
    constructor(nombre, codigo, frase) {
        super(nombre, codigo, frase);
        this.clan = 'Avengers'
    }

}
```

Es muy importante recalcar que el super va antes de todo el codigo a minipular, de los contrario nos dara error. De esta manera ya podremos ver las propiedades para el objeto spiderman:  
`Heroe {nombre: 'Peter Parker', codigo: 'SpiderMan', frase: 'Soy tu amigable vecino Spideman', comida: '', clan: 'Avengers'}`

# Metodos

Ya en este punto se puede manipular la clase como culquier otra, pero digamos que quisieramos utilizar un metodo con el mismo nombre, para ello podemos crearlo :

```
quienSoy() {
        console.log(`Soy ${this.nombre}, ${this.clan}`)

    }
```

Y uno creeria que estamos sobrescribiendo el metodo anterio pero no , podemos mandar a llamar el metodo anterior de la siguiente forma:

```
quienSoy() {
        console.log(`Soy ${this.nombre}, ${this.clan}`)
        super.quienSoy();
    }
```

De esta forma se imprimiria:

```
> Soy Peter Parker, Avengers
> Soy Peter Parker y mi identidad es SpiderMan
```
