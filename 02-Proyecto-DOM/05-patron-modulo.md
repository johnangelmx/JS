# Patron Modulo
El patrón módulo consiste en un módulo donde se encapsulará toda la lógica de nuestra aplicación o proyecto. Dentro de este módulo estarán declaradas todas las variables o funciones privadas y sólo serán visibles dentro del mismo.
# ¿Cómo crear un patrón modulo?
Para crear un patrón módulo se declarará una única variable local que se corresponde con el nombre del módulo. Dicha variable se trata realmente de una función autoejecutable que devuelve un objeto con la funcionalidad que necesitamos, donde las variables internas se llamarán propiedades y las funciones serán métodos.  

Las funciones autoejecutables son aquellas que una vez declaradas se llaman a sí mismas para inicializarse. La peculiaridad de estas funciones es que una vez inicializadas están disponibles en otras partes de la aplicación
```
var miFuncion = (function autoejecutable(){
    'use strict'
    return 'Yo sola me autoejecuto';
})();
```
O de manera de flecha:
```
(()=>{
    'use strict'
    //codigo
})();
```
El `'use strict'`, sirve para que javascript evalue el codigo de forma estandar