# PROG_KOTLIN_PRACTICA_4.8

### 1. ¿Qué es una expresión regular?

Imagina que tienes un campo lleno de vacas de diferentes colores: blancas, marrones, con manchas, etc.

Una **expresión regular** es como una **lista de instrucciones** para encontrar vacas específicas. Por ejemplo, podrías decir:

- "Quiero encontrar todas las vacas que son marrones."
- "Muéstrame solo las vacas que tienen manchas negras y blancas."

La expresión regular es la **regla** que te dice **qué vacas buscar** en el campo.

---

### 2. ¿Para qué se usan?

Las expresiones regulares se usan para encontrar **cosas específicas** en un grupo grande, como cuando quieres:

- Contar cuántas vacas marrones hay en el campo.
- Ver si todas las vacas tienen nombre o alguna está sin identificar.
- Reemplazar a las vacas sin manchas por vacas con manchas.

---

### 3. Explicación con un ejemplo práctico

Supongamos que tienes una lista de vacas con nombres como estos:

```kotlin
val vacas = listOf("Marronita", "Blanquita123", "VacaNegra", "123Manchitas")
```

Ahora quieres encontrar **solo las vacas cuyos nombres contienen números**. Usas una expresión regular:

```kotlin
val regex = Regex(".*\\d+.*")  // Busca nombres con números
val vacasConNumeros = vacas.filter { it.matches(regex) }

println(vacasConNumeros)
```

**Salida:**

```
[Blanquita123, 123Manchitas]
```

**Explicación del patrón `.*\\d+.*`:**

- `.*` → Cualquier cantidad de letras antes o después.
- `\\d+` → Uno o más números (como el "123" en "Blanquita123").

---

### 4. Explicación del Ahorcado con vacas



---

### 5. ¿Qué es una función de extensión?

Imagina que tienes un grupo de vacas y quieres darles habilidades nuevas, como "saltar" o "hacer muuuu".

Una **función de extensión** es como enseñarle una nueva habilidad a todas tus vacas **sin necesidad de cambiar cada vaca manualmente**.

Por ejemplo, podrías agregar una función para que todas las vacas saluden:

```kotlin
fun String.saludarVaca(): String {
    return "¡Muuu! Soy $this"
}

fun main() {
    val vaca = "Blanquita"
    println(vaca.saludarVaca())  // Resultado: ¡Muuu! Soy Blanquita
}
```

---

### 6. Función de extensión `filtrar` para la clase `List<String>`

Vamos a crear una función que filtre solo las vacas que cumplan con un cierto patrón, como si queremos encontrar **solo vacas blancas** usando una expresión regular.

```kotlin
fun List<String>.filtrarVacas(patron: String): List<String> {
    val regex = Regex(patron)
    return this.filter { it.matches(regex) }
}

fun main() {
    val vacas = listOf("VacaBlanca", "VacaNegra", "Blanca123", "Marron")
    val vacasBlancas = vacas.filtrarVacas("^VacaBlanca$")

    println(vacasBlancas)  // Resultado: [VacaBlanca]
}
```

**Explicación:**

1. `List<String>.filtrarVacas` → Creamos la función para una lista de nombres de vacas.
2. `Regex(patron)` → Le damos el patrón de búsqueda, como "VacaBlanca".
3. `filter { it.matches(regex) }` → Devuelve solo las vacas que coinciden.

**Resultado:** Solo se muestra la vaca que tiene el nombre "VacaBlanca".

---


