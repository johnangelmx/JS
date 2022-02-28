# Setters (set)

La sintaxis **set** asocia la propiedad de un objeto a una función que será llamada cuando haya un intento de asignar valor a esa propiedad.
Es decir establecer un valor ,que sera manipulado por el generador de objetos (**la clase**) y tendra la asigancion de una propiedad.  
Tomando el ejemplo anterior:

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

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
    }
}
```

Tomaremos la clase anterior , donde podemos visualizar que tenemos las propiedades a establecer, el constructor listo para asignar los valores a las propiedades y un metodo que imprime el nombre y el codigo (**"la identidad"**).

Digamos que queremos tener una propiedad mas y esta misma su valor lo queremos en mayusculas, pero no podemos dejarle esta tarea al usuario dado que tienden a olvidar, para ello existe los setters, el set establece un valor que podemos utilizarlo de muchas maneras, en este caso asignaremos la propiedad comida en otro apartado ,asiendo asi que se establezca el valor de la propiedad comida en otro apartado del codigo, y que este valor tenga en su cadena letras mayusculas.  
Entendiendo el set , la sintaxis basica:

```
set setName (arguments) {
    // set body
}
```

Los sets siempre tienen que tener un argumento a recibir, y se recomienda unicamente solo asignarle uno , y tambien no pueden terner el mismo nombre que la propiedad,y como recomendacion se debe ingresar en el **setName** el **set** al nombre del mismo set,ahora bien , asignando al apartado "propiedades" en la clase se le agrega la propiedad inicializada `comida = ''`.  
y establecemos el set que este recibira la comida favorita y asignara a la misma:

```
set setComidaFavorita(comida){
    this.comida = comida
}
```

Y para asiganarle todas la letras mayusculas , se usalar el metodo `.toUpperCase();`, que capitaliza todas las letras de la cadena string, es decir, pone en mayusculas el valor, teniendo como resultado:

```
class Persona {
    nombre = ''
    codigo = ''
    frase = ''
    comida = ''

    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
    }
    set setComidaFavorita(comida) {
        this.comida = comida.toUpperCase()
    }
    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
    }

}
```

Hay que entender que la forma en la cual le asignamos valor a la propiedad que se va a crear es la misma que si tuvieramos una propiedad creada comun,osea que no haya sido creada por la clase, ejemplo (`const objeto = {}`) de esta misma manera cuando queremos asignarle un valor a una propiedad,vamos a asignarsela a al objeto creado por el generador de objetos y llamamos al set:

```
spiderman.setComidaFavorita = 'La tarta de fresa de la tia may'
console.log('spiderman')
```

Teniendo como resultado de la impresion:  
`Persona {nombre: 'Peter Parker', codigo: 'SpiderMan', frase: 'Soy tu amigable vecino Spideman', comida: 'EL PIE DE CEREZA DE LA TIA MAY'}`

De esta forma pudimos manipular el valor de una propiedad sin tener que recurrir a hacerlo con un metodo o pedirselo al usuario

# Getters (get)

Enlaza la propiedad de un objeto con una función que será llamada cuando la propiedad es buscada.  
Es decir el get, permite recuperar un valor , que anteriormente fue pre-difinido para que este tenga un valor manipulado u diferente, tomando el ejemplo anterior:

```
class Persona {
    nombre = ''
    codigo = ''
    frase = ''
    comida = ''

    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
    }
    set setComidaFavorita(comida) {
        this.comida = comida.toUpperCase()
    }
    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`)
    }

}
```

Tomando el ejemplo anterior la propiedad **comida** fue manipulada para obtener un valor en mayusculas, el get permite obtener el valor manipulador mas alguna otra manipulacion que queramos asignarle.  
Digamos que queremos la **`comida`** y de la identidad (**`codigo`**) de objeto creado por el generado de objetos (**la clase**) para ello la sintaxis basica de un get:

```
get getName () {
    // get body
    return get;
}
```

Los get's tienden a no recibir ningun argumento , dado que obtendras un valor de un objeto, y siempre tiene que tener su `return`, en este caso tendremos dado el planteamiento anterior lo siguiente:

```
get getComidaFavorita() {
        return `la comida favorita de ${this.nombre} es ${this.comida}`
    }
```

Teniendo como retorno la impresion prevista anteriormente y quedando dentro de la clase de la siguiente forma:

```
class Persona {
    nombre = ''
    codigo = ''
    frase = ''
    comida = ''

    constructor(nombre = 'sin nombre', codigo = 'sin codigo', frase = 'sin frase') {
        this.nombre = nombre
        this.codigo = codigo
        this.frase = frase
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

}
const spiderman = new Persona('Peter Parker', 'SpiderMan', 'Soy tu amigable vecino Spideman')

spiderman.setComidaFavorita = 'La tarta de fresa de la tia may'
```

Como se decia , el get su finalidad es extraer un valor manipulado de un objeto , teniendo asi la forma de asignarlo a una variable , de la siguiente manera:

```
const comidaFavoritaSpiderman = spiderman.getComidaFavorita;
console.log(comidaFavoritaSpiderman)
```

teniendo como resultado:  
`> la comida favorita de Peter Parker es EL PIE DE CEREZA DE LA TIA MAY`

Asi demostrando al utilidad de los setters and getters
