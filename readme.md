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
val nom:String = readLine()!! // !! =ne peut être null ( vide)

val pseudo:String? = null 
nomVide.readLine() // peut être null ( pas rempli ) 

println("Le nom $nom est composé de ${nom.length}") // String template
```

**Avec mise en forme plus poussée**

**trimIndent()** permet de supprimer les espaces blancs provoqué par la tabulation

```java
val retour:String = """
    Votre nom et prénom $nom $prenom,
    votre pseudo : $pseudo,
    votre mail : $mail, 
    adresse : $rue $numero
                $ville 
                $codePostal
""".trimIndent()
```

## Range : entre 2 valeurs

```java
val r1 : IntRange = 1..5 // de 1 à 5
val r2 : IntRande = 1.RangeTo(5) // avec la méthode
val r3 : 1 until 5 // range de 1 à 4 (5 est non compris)
val r4 : 5 downTo 1 // décroissant

val r5 IntProgression = 1..5 step 2 // avec un interval 1-3-5
val r6 IntProgression = 1.RangeTo(5) step 2
val r7 : 1 until 5 step 2
```
## Appartenance à une plage de valeur

```java
// Méthode contains
val plageAO = "A" .. "O"
val lettre1 = "C"
val value = plageAO.contains(lettre1)
println(value) // true

print("Entrez un chiffre")
val value:Int = readLine()!!.toInt() // toInt pcq c'est un nombre et que redline envoie un string
val entre = (0..5).contains(value)
println(entre) // true

// Utilisation de l'opérateur in
val entreZeroEt5 = value in 0..5
val pasEntreZeroEt5 = value !in 0..5
```

## Conditionnels

## if

```java
    println("Entre un nombre")
    val annee : Int = readLine()!!.toInt() // toInt pcq c'est un nombre et que redline envoie un string
    if ((annee % 4 == 0 && annee % 100 > 0) || (annee % 400 == 0) )
        println("$annee est bissextile")
    else
        println("$annee n'est pas bissextile")
```

## when 

Permet de réaliser plusieurs test sur des valeurs

```java
println("Entre un nombre entre 0 et 20")
val number : Int = readLine()!!.toInt()

val grade = when (number) {
    !in 0..20 -> null // si le chiffre n'est pas entre 0 et 20
    20 -> "Excellent"
    in 17..19 -> "Très bien"
    in 13..16 -> "Bien"
    in 10..12 -> "Suffisant"
    in 8..9 -> "Insuffisant"
    else -> "Vaux mieux que j'dise rien"
}
println("Votre grade : $grade ")
```

## Boucle

### while

### do while

```java
println("Veuillez encoder un chiffre entre 0 et 10")
var input: Int
do {
    println("/ ")
    input = readLine()!!.toInt()
} while (input < 0 || input > 0)
```

### for

```java
// Parcourir les éléments
for (value: Sting in nom) {
    println("vaut $value")
}
// Parcourir les indices
 for(i in nom.indices) {
     println("l'element est à l'index $i et vaut ${nom[i]}")
}
// index + valeur    
for((index, valeur) in nom.withIndex()) {
    println("L'élément à l'index $index vaut $value")
}

// Parcourir des plages de valeurs
for(i in 1..10) {
    println("$i")
}
```
## Savoir si un nombre est un nombre premier

```java
    var estPremier : Boolean = false
    if (nombre ==2) {
        estPremier = true
    }
    else if (nombre > 2 && nombre % 2 !== 0) { // plus grand que 2 et n'est pas paire
        val division = 3 until nombre step 2 // a partir de 3 jusqu'au nombre par saut de 2 (on a pas besoin des pairs)

        for(div: Int in division) {
            if(nombre % div == 0) {
                estPremier = false;
                break;
            }
        }
    }
    if(estPremier){
        println("Le nombre $nombre est un nombre premier")
    }
    else {
        println("Le nombre $nombre n'est pas un nombre premier")
    }
```