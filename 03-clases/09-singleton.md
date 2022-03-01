# Singleton

El singleton es una manera de ejecutar tu clase una sola vez ,esto con la utilidad que puedas ingresar solo un usuario mas , aparte de los demas que tuviste o compartir tu codigo o tu instancia de la clase con otro programador y que el solo pueda ejecutarlo solo una vez.  
Es decir, singleton instancia unica de mi clase.

Para ello examinaremos el siguiente codigo:

```
class Singleton {
    static #instancia; //undefined
    nombre = ''
    constructor(nombre = '') {

        if (Singleton.#instancia) {
            return Singleton.#instancia
        } else {
            Singleton.#instancia = this
            this.nombre = nombre
        }
        // return this
    }
}

const instancia1 = new Singleton('Ironman')
const instancia2 = new Singleton('Spiderman')
const instancia3 = new Singleton('BlackPanther')
console.log(`nombre en la instancia es : ${instancia1.nombre}`)
console.log(`nombre en la instancia es : ${instancia2.nombre}`)
console.log(`nombre en la instancia es : ${instancia3.nombre}`)
```

**La finalidad del codigo es poder utilizarlo una unica ocacion y que este si se quiere generar un segundo objeto , el resultado sera el mismo que el primero creado**

Como podermos observar tiene la clase creada como cualquier clase.  
Contiene un parametro privado y un parametro publico y el contructor con el argumento de nombre.  
Para poder proteger el codigo la siguiente forma de control (if-else), dicta lo siguiente, si la variable #instancia contiene un false(lo cual en primer momento NO lo es, dado que undefined = false) , se ejecutara el (else) el cual asigna el return de lo que genera la clase y envia el el objeto con el nombre asignado, en dado caso que que si tenga un resultado `#instancia` esto se considera como true, y a su vez unicamente retornara el primer objeto generado, dando como resultado:

```
> nombre en la instancia es : Ironman
> nombre en la instancia es : Ironman
> nombre en la instancia es : Ironman
```
Protegiendo asi que se genere un nuevo objeto.