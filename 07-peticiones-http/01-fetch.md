# Fetch

La API Fetch proporciona una interfaz JavaScript para acceder y manipular partes del canal HTTP, tales como peticiones y respuestas. También provee un método global `fetch()` que proporciona una forma fácil y lógica de obtener recursos de forma asíncrona por la red.  
Es decir permite la obtencion de datos atraves de la web, en este caso trabajeremos para la obtencionde un JSON.

Para la obtencionde datos usaremos (https://api.chucknorris.io/), que la peticion la haremos atraves de su link:

(https://api.chucknorris.io/jokes/random)

Y que el ejemplo de la respuesta seria:

```
{
"icon_url" : "https://assets.chucknorris.host/img/avatar/chuck-norris.png",
"id" : "JyOoOwUYSY22fo0NN3qGFQ",
"url" : "",
"value" : "a man once heard two guys talking about Chuck Norris.He went home and decided to look up who Chuck Norris is? He was suprised when it came to a blank screen, he tryed to click out of it untill a window popped up please wait. He waited a while a bar appeared saying now uploading Chuck Norris.He looked stuned when Chuck Norris crawled out of his computer to round house kick him in the face. this man now knows every fact about Chuck Norris."
}
```

## Sintaxis Basica

```
function fetch(input: RequestInfo, init?: RequestInit): Promise<Response>
```

Como podemos observar se necesita del un **RequestInfo**, `input: RequestInfo`:  
Que es como se le conoce al link de la cual se hara la peticion  
Y tiene una configuracion **RequestInit** `init?: RequestInit`: Proximo a porfundizar

Tambien se puede observar que es una promesa, asi que se puede usar y manipular como cualquier otra promesa

# Usando el fetch

Creamos una variable que almacenara el link de que nos proporciona la pagina a la cual haremos una peticion:

```
const jokeURL = 'https://api.chucknorris.io/jokes/random'
```

Y creamos la peticion imprimiendo si es una respuesta positiva por parte de la peticion el contenido de la misma:

```
fetch(jokeURL).then((respuesta) => {
    console.log(respuesta)
})
```

Obteniendo el siguiente resultado:

```
Response {type: 'cors', url: 'https://api.chucknorris.io/jokes/random', redirected: false, status: 200, ok: true, …}
body: (...)
bodyUsed: false
headers: Headers {}
ok: true
redirected: false
status: 200
statusText: ""
type: "cors"
url: "https://api.chucknorris.io/jokes/random"
[[Prototype]]: Response
```

El cual podemos observar informacion importante ,pero la que se recalcaria es la siguiete:

`status: 200`, permite ver que la peticion no tuvo problemas  
`ok: true` Acepta que la peticion fue respondida

# Extrayendo la informacion de la peticion

Como habiamos comentado lo que recibe esta peticion es un JSON , por eso al pedir la informacion de la respuesta, podemos extaer la informacion con la funcion `.json()` recordadndo que esta funcion es una promesa

```
fetch(jokeURL).then((respuesta) => {
    respuesta.json().then((data)=>{
        console.log(data)
    })

})
```

Obteniendo:

```
{categories: Array(0), created_at: '2020-01-05 13:42:23.880601', icon_url: 'https://assets.chucknorris.host/img/avatar/chuck-norris.png', id: 'Ez3DTqMYSLCay1qoBNyZiw', updated_at: '2020-01-05 13:42:23.880601', …}

categories: []
created_at: "2020-01-05 13:42:23.880601"
icon_url: "https://assets.chucknorris.host/img/avatar/chuck-norris.png"
id: "Ez3DTqMYSLCay1qoBNyZiw"
updated_at: "2020-01-05 13:42:23.880601"
url: "https://api.chucknorris.io/jokes/Ez3DTqMYSLCay1qoBNyZiw"
value: "What would a Klondike bar do for Chuck Norris?"
[[Prototype]]: Object
```

Teniendo ahora si los datos de la peticion inicial.  
Datos que se pueden desestructurar de manera normal, por ejemplo si queremos extraer el identificador `id` y la broma `value`:

```
fetch(jokeURL).then((respuesta) => {
    respuesta.json().then(({id,value})=>{
        console.log(`Este es el id:  ${id}`)
        console.log(`Este es el value:  ${value}`)
    })

})
```

Teniendo como resultado:

```
>Este es el id:  tE-xHJmRSzi7P_5GLq530A
>Este es el value:  Chuck Norris can smell puss from 50 yards.
```

# Anidando Promesas

Como podemos observar nuesto codigo empieza a toma forma de callback hell, cosa que las promesas tienden a resolver.

Por ejemplo cuando queremos anidar promesas podemos retornar en el `then` la promesa que queremos utilizar y asi mismo ese `.then(Promesa-retornada)` se puede utilizar como lo hacemos con las promesas, asi es, podemos adherirle un `then` , pudiendo asi manipular la informacionde la promesa como queramos, sin ver el callback hell y teniendo mejor utilidad.

Ejemplo:

```
fetch(jokeURL).then(respuesta => respuesta.json()).then(({id,value})=>{
    console.log(`Este es el id:  ${id}`)
    console.log(`Este es el value:  ${value}`)
})
```

Teniendo como resultado:

```
> Este es el id:  Qw17fKlcS4qojaU6nyFncg
> Este es el value:  FATWA senders-- Molly Norris is Chuck Norris's little sister
```
