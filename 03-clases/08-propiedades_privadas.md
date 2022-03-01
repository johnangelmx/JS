# Propiedades privadas

Las propiedades de la clase son públicas de forma predeterminada y se pueden examinar o modificar fuera de la clase. Sin embargo, existe una propuesta experimental para permitir la definición de campos de clase privados utilizando un #prefijo hash.  
Los campos privados son accesibles en el constructor de clases desde dentro de la propia declaración de clases.

En pocas palabras las propiedades privadas de una clase, sirven para ejecutarlas unicamente dentro de la clase ,para que no puedan ser manipuladas fuera de este mismo.  
Para ellos utilizamos lo anterior dicho el hash **(**#**)**  
Ejemplo:

```
class Rectangulo {

    area = 0

    constructor(base = 0, altura = 0) {
        this.base = base
        this.altura = altura
        this.area = base * altura
    }
}
```

Creamos un objeto y lo imprimimos

```
const rectangulo = new Rectangulo (10,15)

console.log(rectangulo)
```

Teniendo como resultado  
`Rectangulo {area: 150,base: 10, altura: 15}`
Pero como habiamos comentado en el apartado anterior , estas misma son propiedades publicas y pueden ser manipuladas desde afuera de la clase  
Por ejemplo:

```
rectangulo.area = 100

console.log(rectangulo)
```

Teniendo como resultado:  
`Rectangulo {area: 100,base: 10, altura: 15}`  
Para ello existen las propiedades privadas

# Propiedades privadas

El uso de las misma consta de usar el hash (#) antes del nombre del parametro:

```
class Rectangulo {

    #area = 0

    constructor(base = 0, altura = 0) {
        this.base = base
        this.altura = altura
        this.#area = base * altura
    }
}
const rectangulo = new Rectangulo (10,15)
```

y si intentamos manipularlo:

```
rectangulo.area = 100

console.log(rectangulo)
```

Tendremos como resultado el siguiente error:  
`Uncaught SyntaxError: Private field '#area' must be declared in an enclosing class`

Haciendo asi nuestra parametro de la clase inalcanzable detro del codigo u otras paginas dentro de nuesto proyecto

# Metodos Privados

El uso de las misma consta de usar el hash (#) antes del nombre del metodo:

```
class Rectangulo {

    #area = 0

    constructor(base = 0, altura = 0) {
        this.base = base
        this.altura = altura
        this.#area = base * altura
    }
    #calcularArea() {
        console.log(this.#area * 2)
    }

}

const rectangulo = new Rectangulo(10, 15)

```

y si intentamos manipularlo:

```
rectangulo.#calcularArea();
```

Tendremos como resultado el siguiente error:  
`Uncaught SyntaxError: Private field '#calcularArea' must be declared in an enclosing class`

Haciendo asi nuestro metodo de la clase inalcanzable detro del codigo u otras paginas dentro de nuesto proyecto
