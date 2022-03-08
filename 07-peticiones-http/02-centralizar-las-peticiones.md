# Centralizar la peticiones

Es recomendable y estandarizado tener las peticones en un solo archivo denominado:
**http-provider.js**

Dentro del mismo proporcionaremos el **RequestInfo**, `input: RequestInfo`.  
En nuestro caso sigue siendo el:

```
const jokeURL = "https://api.chucknorris.io/jokes/random";
```

# Mejorando la practica del fetch

Para poder hacer peticiones mas correctas y asícronas , necesitaremos definir las funciones en Funcion-Promesa, es decir agregando el asíncronismo y la respuesta espera de nuestras promesas(`async`, `await`)

```
const obtenerChiste = async()=>{
    const resp = await fetch(jokeURL)
    if(!resp.ok) return alert('La peticion fue rechazada')
    return await resp.json();
}
```

**Y recordando que como es una Funcion-Promesa , para acceder a ella usaremos el then**

```
obtenerChiste().then(console.log)
```

obteniendo asi:

```
{categories: Array(0), created_at: '2020-01-05 13:42:28.984661', icon_url: 'https://assets.chucknorris.host/img/avatar/chuck-norris.png', id: 'u5o2zLdkT7G9Tiwzm922wg', updated_at: '2020-01-05 13:42:28.984661', …}
categories: []
created_at: "2020-01-05 13:42:28.984661"
icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
id: "u5o2zLdkT7G9Tiwzm922wg"
updated_at: "2020-01-05 13:42:28.984661"
url: "https://api.chucknorris.io/jokes/u5o2zLdkT7G9Tiwzm922wg"
value: "Chuck Norris doesn't fly, gravity collapses around him."
```

# Manejo de errores

El objetivo del apartado anterior es simple la obtencion de datos con **Funcion-Promesa**.

Pero para el manejo de errores en promesas asíncronas sabemos que existe el try y el catch, asi que trabajemos con ello y con la desestructuracion de elemento en el:

```
const obtenerChiste = async()=>{
    try{

    const resp = await fetch(jokeURL)
    if(!resp.ok) throw `La peticion fue rechazada`
    const {icon_url,id,value} = await resp.json();
    return {icon_url,id,value}
    }catch(error){

         throw error

    }


}

```

Teniendo como resultado:

```
{icon_url: 'https://assets.chucknorris.host/img/avatar/chuck-norris.png', id: '6UUb1yloR1SC9hn3nTtozA', value: 'Chuck Norris is the only person who can gang up on you.'}
> icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
> id: "6UUb1yloR1SC9hn3nTtozA"
> value: "Chuck Norris is the only person who can gang up on you."
 [[Prototype]]: Object
```
Como podemos observar el `throw` es muy importante como declaracion del problema , porque es aquella llamada de palabra reservada la cual dentra el codigo del programa si algo sale mal, bien podemos continuar el programa declarando en el catch, un retorno de un objeto vacio u diferente , pero en este caso retomaremos el de romper el codigo 