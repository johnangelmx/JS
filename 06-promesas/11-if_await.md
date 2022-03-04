# If await

```
const heroeIfAwait = async (id) => {
    if ( (await buscarHeroeAsync('iron')).nombre === 'Ironman') {
        console.log('Es el mejor de todos')
    } else {
        console.log('Naaa!')
    }
}
```

Como lo observamos en el apartado anterior , la forma en la cual podemos evaluar una promesa y obtener su resultado es asignandolo en este caso, antes de llamarlo , es decir en los parametros.