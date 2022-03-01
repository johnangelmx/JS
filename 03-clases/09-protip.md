# Multi constructores

```
class Persona {
    static porObjeto({ nombre, apellido, pais }) {
        return new Persona(nombre, apellido, pais)
    }
    constructor(nombre, apellido, pais) {
        this.nombre = nombre
        this.apellido = apellido
        this.pais = pais
    }
    getInfo() {
        console.log(`Informacion: ${this.nombre}, ${this.apellido}, ${this.pais}`)
    }
}
const nombre1 = 'Melissa',
    apellido1 = 'Flores',
    pais1 = 'Honduras'

const fher = {
    nombre: 'Fernando',
    apellido: 'Herrera',
    pais: 'Costa Rica'
}

const persona1 = new Persona(nombre1, apellido1, pais1)
const persona2 = Persona.porObjeto(fher)
persona1.getInfo()
persona2.getInfo()


```

Apartir del codigo anterior se puede crear multiples constructores.

Para ello de manera simplificada se hace creando un metodo estatico que poniendo el ejemplo si quiero que mi clase reciba un objeto con las mismas propiedades:

```
const fher = {
    nombre: 'Fernando',
    apellido: 'Herrera',
    pais: 'Costa Rica'
}
```

Podemos crear el metodo para que este regrese el objeto pero de forma que la clase lo entienda:

```
static porObjeto({ nombre, apellido, pais }) {
        return new Persona(nombre, apellido, pais)
    }
```

Y para crearlo y asignarlo se hace:

```
const persona2 = Persona.porObjeto(fher)
```

Teniendo como resultado el objeto creado por la misma clase:

```
> Informacion: Fernando, Herrera, Costa Rica
```
