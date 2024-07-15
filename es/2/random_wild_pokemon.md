<!-- Add translation for the following page: https://learn.vyperlang.org/#/2/random_wild_pokemon
Do NOT change the code below. The below code runs the code editor -->

# Capítulo 5: Crear un Pokemon Aleatorio Salvaje

En el capítulo anterior, iniciamos nuestro contrato con 20 nombres de pokemon. Ahora es el momento de luchar ⚔️

## Función con multiples valores de retorno

Una función puede tambien retornar multiples valores de retorno como en el siguiente ejemplo:

    struct Student:
        name: String[32]
        age: uint256

    # un mapeo entre el número de roll y
    # los detalles del estudiante
    studentList: HashMap[uint256, Student]

    @external
    def getPersonDetails(rollNumber: uint256) -> (String[32], uint256):
        student: Student = self.studentList[rollNumber]
        return student.name, student.age

## Ponlo a prueba

1. Crea una función `@external` llamada `battle` que tenga 1 parámetro de entrada: `pokemon` de tipo `Pokemon`. Esta función debe devolver 4 parámetros: `bool`, `String[32]`, `uint256`, `uint256`.

2. Dentro de la función `battle`, crea una variable `uint256` llamada `randomDNA`. Ahora llama a la función `_generateRandomDNA` y asigna su salida a `randomDNA`.

3. Dentro de la función `battle`, crea una variable `String[32]` llamada `randomName`. Ahora para asignar un valor a `randomName`, tenemos que seleccionar un nombre aleatorio de `pokemonNames` pasando cualquier `uint256` de `0` a `19` como clave. Podemos generar un `uint256` aleatorio adecuado mediante la siguiente operación: `randomDNA` modulus `NAME_MODULUS`.

4. Dentro de la función `battle`, crea una variable `uint256` llamada `randomHP`. Establece su valor igual al resultado de la operación módulo: `randomDNA` (`%`) `HP_LIMIT`.

<!-- tabs:start -->

#### ** Template **

[embedded-code](../../assets/2/2.5-template-code.vy ':include :type=code embed-template')

#### ** Solution **

[embedded-code-final](../../assets/2/2.5-finished-code.vy ':include :type=code embed-final')

#### ** Previous Chapter Solution **

[embedded-code-previous](../../assets/2/2.4-finished-code.vy ':include :type=code embed-previous')

<!-- tabs:end -->
