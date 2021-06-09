# Kotlin

## Variable

**constante** : `val prenom : String = "Marie"`
**ré-affectable** : `var argent : Double = 1_000_000.0` . On a le droit de mettre des tirets. ca rend aussi le code plus lisible
**nulle** : pour déclarer une variable nulle il faut rajouter ? après son type

```java
 var rue:String? = null
```

**Converstion**

toByte(), toShort(), toInt(), toLong(), toFloat(), toDouble(), toChar()

```java
val nbByte: Byte = 42
val nbInt: Int = nbByte.toInt() // conversion explicite
```

## Chaines de caractères String

```java
println("Veuillez entrer un nom")
val nom:String = readLine()!!
println("Le nom $nom est composé de ${nom.length}") // String template
```

**Avec mise en forme plus poussée**

```java
val retour:String = """
    Votre nom et prénom $nom $prenom,
    $pseudo,
    $mail, 
    adresse : $rue $numero
                $ville 
                $codePostal
""".trimIndent()
```