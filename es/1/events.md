<!-- Add translation for the following page: https://learn.vyperlang.org/#/1/events
Do NOT change the code below. The below code runs the code editor -->

# Capítulo 13: Eventos

¡Nuestro contrato está casi terminado! Ahora vamos a añadir un `evento`.

Los **Eventos** son una manera para que tu contrato comunique que algo paso en la blockchain a tu aplicación front-end, la cual puede ‘escuchar’ por ciertos eventos y tomar acciones cuando estos ocurren.

### Ejemplo

```Vyper
# declarar un evento
event NewPersonAdded:
	name: String[64]
	agre: uint256

people: HashMap[String[64], uint256]

@external
Def addNewPerson(name: String[64], uint256, age: uint256):
	Self.people[name] = age

	# Dispara un evento para que la función sepa que la función fue llamada
	Log NewPersonAdded(name, age)
```

Tu aplicación front-end ahora podrá escuchar al evento. Una implementación de javascript se vería así:

```js
YurContract.NewPersonAdded(function(error, result) {
	// hace algo con el resultado
}
```

# Ponlo a prueba

Queremos un evento que haga saber a nuestro front-end cada vez que un nuevo Pokemon es creado, así la aplicación podrá mostrarlo.

1. Crea un evento llamado `NewPokemonCreated`. Debería tener 3 argumentos:

   - `name` de tipo `String[32]`
   - `dna` de tipo `uint256`
   - `HP` de tipo `uint256`

2. Usar la palabra clave `log` para disparar el evento dentro de la función `_createPokemon` antes de la sentencia `return`.

Felicidades 🎉

Haz completado la lección 1 de Vyper.fun y ahora tienes el poder de crear nuevos Pokemon en el blockchain usando Vyper 🔥

¡Tweetea sobre ello para compartir tu asombrosa hazaña!!

[![Tweet](https://img.shields.io/twitter/url?style=social&url=https%3A%2F%2Fvyper.fun%2F%23%2F1%2Fintroduction)](https://twitter.com/intent/tweet?hashtags=VyperFun&ref_src=twsrc%5Etfw&text=Acabo%20de%20completar%20la%20leccion%201%3A%20Crea%20tu%20Pok%C3%A9mon%20en%20la%20blockchain%20usando%20%40vyperlang%20con%20%40VyperFun%20%F0%9F%98%8E%20&tw_p=tweetbutton&url=https%3A%2F%2Fvyper.fun%2F%23%2F1%2Fintroduction)

<!-- tabs:start -->

#### ** Template **

[embedded-code](../../assets/1/1.13-template-code.vy ':include :type=code embed-template')

#### ** Solution **

[embedded-code-final](../../assets/1/1.13-finished-code.vy ':include :type=code embed-final')

#### ** Previous Chapter Solution **

[embedded-code-previous](../../assets/1/1.12-finished-code.vy ':include :type=code embed-previous')

<!-- tabs:end -->
