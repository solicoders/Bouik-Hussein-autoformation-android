# Autoformation  Android 

1. Avant de commencer
Dans un atelier de programmation précédent, vous avez découvert un programme simple qui imprime Hello, world!. Dans les programmes que vous avez écrits jusqu'à présent, deux fonctions étaient récurrentes :

Une fonction main(), qui est requise dans chaque programme Kotlin. Il s'agit du point d'entrée (ou point de départ) du programme.
Une fonction println(), que vous avez appelée depuis main() pour générer du texte.
Dans cet atelier de programmation, vous allez vous familiariser davantage avec les fonctions.

Les fonctions vous permettent de diviser le code en éléments réutilisables, plutôt que d'inclure tous les éléments dans main(). Il s'agit de composants essentiels dans les applications Android. Apprendre à les définir et à les utiliser est une étape cruciale dans votre parcours de développeur Android.

Conditions préalables
Vous connaissez les bases de la programmation en Kotlin, y compris les variables, et les fonctions println() et main().
Points abordés
Définir et appeler vos propres fonctions
Renvoyer des valeurs à partir d'une fonction que vous pouvez stocker dans une variable
Définir et appeler des fonctions avec plusieurs paramètres
Appeler des fonctions avec des arguments nommés
Définir des valeurs par défaut pour les paramètres des fonctions
Ce dont vous avez besoin
Un navigateur Web ayant accès à Kotlin Playground

2. Définir et appeler une fonction
Avant d'examiner en détail les fonctions, penchons-nous sur quelques termes de base.

La déclaration (ou la définition) d'une fonction utilise le mot clé fun et inclut du code entre accolades qui contient les instructions nécessaires à l'exécution d'une tâche.
L'appel d'une fonction entraîne l'exécution de tout le code qu'elle contient.
Jusqu'à présent, vous avez écrit tout votre code dans la fonction main(). La fonction main() n'est appelée nulle part dans le code. Le compilateur Kotlin l'utilise comme point de départ. La fonction main() vise uniquement à inclure d'autres extraits de code que vous souhaitez exécuter, tels que des appels à la fonction println().

La fonction println() fait partie du langage Kotlin. Cependant, vous pouvez définir vos propres fonctions. Vous pouvez ainsi réutiliser votre code si vous devez l'appeler plusieurs fois. Prenons l'exemple du programme suivant.


fun main() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
La fonction main() comprend deux instructions println() : l'une pour souhaiter un joyeux anniversaire à Rover et l'autre pour indiquer l'âge de Rover.

Bien que Kotlin vous permette de placer tout votre code dans la fonction main(), cette approche n'est pas toujours conseillée. Par exemple, si vous souhaitez également que votre programme contienne le message "Bonne année", la fonction principale devra également inclure ces appels à println(). Ou peut-être voulez-vous souhaiter un joyeux anniversaire à Rover plusieurs fois. Dans ce cas, vous pouvez simplement copier et coller le code, ou créer une fonction distincte pour le message d'anniversaire. La deuxième approche est celle que vous allez utiliser. La création de fonctions distinctes pour des tâches spécifiques présente plusieurs avantages.

Code réutilisable : au lieu de copier et coller le code dont vous avez besoin plusieurs fois, vous pouvez appeler une fonction chaque fois que nécessaire.
Lisibilité : lorsque vous vous assurez que les fonctions effectuent une tâche bien spécifique, les autres développeurs, vos collègues et vous-même savez toujours exactement ce à quoi sert l'extrait de code.
La syntaxe permettant de définir une fonction est présentée dans le schéma suivant.

b44a09e0004280fe.png

Une définition de fonction commence par le mot clé fun, suivi du nom de la fonction, d'un ensemble de parenthèses d'ouverture et de fermeture, puis d'un ensemble d'accolades d'ouverture et de fermeture. Le code qui s'exécute lorsque la fonction est appelée se trouve entre les accolades.

Vous allez maintenant créer une fonction pour évacuer les deux instructions println() de la fonction main().

Dans votre navigateur, ouvrez Kotlin Playground et remplacez le contenu par le code suivant.

fun main() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
Après la fonction main(), définissez une nouvelle fonction nommée birthdayGreeting(). Cette fonction est déclarée selon la même syntaxe que main().

fun main() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}

fun birthdayGreeting() {

}
Déplacez les deux instructions println() de main() pour qu'elles apparaissent entre les accolades de la fonction birthdayGreeting().

fun main() {

}

fun birthdayGreeting() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
Dans la fonction main(), appelez la fonction birthdayGreeting(). Le code final devrait ressembler à ce qui suit :

fun main() {
    birthdayGreeting()
}

fun birthdayGreeting() {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
Exécutez votre code. Vous devriez voir la sortie suivante :

Happy Birthday, Rover!
You are now 5 years old!

3. Renvoyer une valeur à partir d'une fonction
Dans les applications plus complexes, les fonctions ne se limitent pas à l'impression de texte.

Les fonctions Kotlin peuvent également générer des données appelées valeur de retour, qui sont stockées dans une variable que vous pouvez utiliser ailleurs dans le code.

Lorsque vous définissez une fonction, vous pouvez spécifier le type de données de la valeur à renvoyer. Pour spécifier le type renvoyé, placez deux-points (:) après les parenthèses et le nom d'un type (Int, String, etc.) après les deux-points. Un seul espace est placé après le type renvoyé et avant l'accolade d'ouverture. Dans le corps de la fonction, après toutes les instructions, utilisez une instruction return pour spécifier la valeur que la fonction doit renvoyer. Une instruction return se compose du mot clé return suivi de la valeur (une variable, par exemple) que la fonction doit renvoyer comme résultat.

La syntaxe permettant de déclarer une fonction avec un type renvoyé est la suivante.

268729385928f66f.png

Type Unit
Par défaut, si vous ne spécifiez pas de type renvoyé, le type par défaut est Unit. Unit signifie que la fonction ne renvoie pas de valeur. Unit équivaut à des types renvoyés vides dans d'autres langages (void en Java et C, Void/tuple vide () en Swift, None en Python, etc.). Toute fonction qui ne renvoie pas de valeur renvoie implicitement Unit. Pour en faire l'expérience vous-même, modifiez votre code pour renvoyer Unit.

Dans la déclaration de la fonction birthdayGreeting(), ajoutez le signe deux-points après la parenthèse de fermeture, puis spécifiez le type renvoyé Unit.

fun main() {
    birthdayGreeting()
}

fun birthdayGreeting(): Unit {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
Exécutez le code et vérifiez que tout continue à fonctionner.

Happy Birthday, Rover!
You are now 5 years old!
Il n'est pas obligatoire de spécifier le type renvoyé Unit en Kotlin. Pour les fonctions qui ne renvoient rien ou qui renvoient Unit, vous n'avez pas besoin d'une instruction return.

Remarque : Le type Unit sera également abordé lorsque vous découvrirez une fonctionnalité Kotlin appelée "lambdas" dans un prochain atelier de programmation.

Renvoyer une chaîne (String) à partir de birthdayGreeting()
Pour expliquer comment une fonction peut renvoyer une valeur, vous devez modifier la fonction birthdayGreeting() pour qu'elle renvoie une chaîne au lieu d'imprimer le résultat.

Remplacez le type renvoyé Unit par String.

fun birthdayGreeting(): String {
    println("Happy Birthday, Rover!")
    println("You are now 5 years old!")
}
Exécutez votre code. Un message d'erreur s'affiche. Si vous déclarez un type renvoyé pour une fonction (par exemple, String), cette fonction doit inclure une instruction return.

A 'return' expression required in a function with a block body ('{...}')
Vous ne pouvez renvoyer qu'une seule chaîne à partir d'une fonction, et non deux. Remplacez les instructions println() par deux variables, nameGreeting et ageGreeting, à l'aide du mot clé val. Comme vous avez supprimé les appels à println() dans birthdayGreeting(), l'appel de birthdayGreeting() n'imprime rien.

fun birthdayGreeting(): String {
    val nameGreeting = "Happy Birthday, Rover!"
    val ageGreeting = "You are now 5 years old!"
}
En vous basant sur la syntaxe de mise en forme de chaîne que vous avez apprise dans un atelier de programmation précédent, ajoutez une instruction return pour renvoyer une chaîne composée des deux messages de félicitations à partir de la fonction.
Pour mettre en forme les messages de félicitations sur une ligne distincte, vous devez également utiliser le caractère d'échappement \n. Il est semblable au caractère d'échappement \" que vous avez étudié dans un atelier de programmation précédent. Le caractère \n indique un retour à la ligne et fait en sorte que les deux messages de félicitations se trouvent chacun sur une ligne distincte.


fun birthdayGreeting(): String {
    val nameGreeting = "Happy Birthday, Rover!"
    val ageGreeting = "You are now 5 years old!"
    return "$nameGreeting\n$ageGreeting"
}
Dans main(), comme birthdayGreeting() renvoie une valeur, vous pouvez stocker le résultat dans une variable de chaîne. Déclarez une variable greeting à l'aide de val pour stocker le résultat de l'appel de birthdayGreeting().

fun main() {
    val greeting = birthdayGreeting()
}
Dans main(), appelez println() pour imprimer la chaîne greeting. La fonction main() devrait désormais se présenter comme suit.

fun main() {
    val greeting = birthdayGreeting()
    println(greeting)
}
Exécutez votre code, puis observez que le résultat est le même qu'avant. Le renvoi d'une valeur vous permet de stocker le résultat dans une variable, mais que se passe-t-il si vous appelez la fonction birthdayGreeting() dans la fonction println() ?

Happy Birthday, Rover!
You are now 5 years old!
Supprimez la variable, puis transmettez le résultat de l'appel de la fonction birthdayGreeting() à la fonction println() :

fun main() {
    println(birthdayGreeting())
}
Exécutez votre code et observez le résultat. La valeur renvoyée lors de l'appel de birthdayGreeting() est transmise directement à println().

Happy Birthday, Rover!
You are now 5 years old!

4. Ajouter un paramètre à la fonction birthdayGreeting()
Comme vous avez pu le constater, lorsque vous appelez println(), vous pouvez inclure une chaîne entre parenthèses ou transmettre une valeur à la fonction. Vous pouvez faire de même avec la fonction birthdayGreeting(). Toutefois, vous devez d'abord ajouter un paramètre à birthdayGreeting().

Un paramètre spécifie le nom d'une variable et un type de données que vous pouvez transmettre à une fonction en tant que données accessibles au sein de cette fonction. Les paramètres sont déclarés entre parenthèses après le nom de la fonction.

9bf915c1980799ff.png

Chaque paramètre comprend un nom de variable et un type de données, séparés par le signe deux-points et un espace. Pour utiliser plusieurs paramètres, séparez-les par une virgule.

Pour l'instant, la fonction birthdayGreeting() sert uniquement à souhaiter un joyeux anniversaire à Rover. Vous allez maintenant ajouter un paramètre à la fonction birthdayGreeting() afin de souhaiter un joyeux anniversaire à tous les noms que vous lui transmettez.

Entre les parenthèses de la fonction birthdayGreeting(), ajoutez un paramètre name de type String à l'aide de la syntaxe name: String.

fun birthdayGreeting(name: String): String {
    val nameGreeting = "Happy Birthday, Rover!"
    val ageGreeting = "You are now 5 years old!"
    return "$nameGreeting\n$ageGreeting"
}
Le paramètre défini à l'étape précédente fonctionne comme une variable déclarée avec le mot clé val. Sa valeur peut être utilisée n'importe où dans la fonction birthdayGreeting(). Dans un atelier de programmation précédent, vous avez vu comment insérer la valeur d'une variable dans une chaîne.

Remplacez Rover dans la chaîne nameGreeting par le symbole $ suivi du paramètre name.

fun birthdayGreeting(name: String): String {
    val nameGreeting = "Happy Birthday, $name!"
    val ageGreeting = "You are now 5 years old!"
    return "$nameGreeting\n$ageGreeting"
}
Exécutez votre code et observez l'erreur. Maintenant que vous avez déclaré le paramètre name, vous devez transmettre une chaîne (String) lorsque vous appelez birthdayGreeting(). Lorsque vous appelez une fonction qui utilise un paramètre, vous lui transmettez un argument. L'argument correspond à la valeur que vous transmettez, par exemple "Rover".

No value passed for parameter 'name'
Transmettez "Rover" à l'appel birthdayGreeting() dans main().

fun main() {
    println(birthdayGreeting("Rover"))
}
Exécutez votre code et observez le résultat. Le nom "Rover" provient du paramètre name.

Happy Birthday, Rover!
You are now 5 years old!
Comme birthdayGreeting() utilise un paramètre, vous pouvez l'appeler avec un autre nom que "Rover". Ajoutez un autre appel à birthdayGreeting() dans l'appel à println(), en transmettant l'argument "Rex".

println(birthdayGreeting("Rover"))
println(birthdayGreeting("Rex"))
Exécutez à nouveau le code, puis observez que la sortie diffère en fonction de l'argument transmis dans birthdayGreeting().

Happy Birthday, Rover!
You are now 5 years old!
Happy Birthday, Rex!
You are now 5 years old!
Remarque : Bien qu'ils soient souvent utilisés de façon interchangeable, un paramètre et un argument sont deux concepts distincts. Lorsque vous définissez une fonction, vous spécifiez les paramètres qui lui sont transmis lorsqu'elle est appelée. Lorsque vous appelez une fonction, vous transmettez des arguments correspondant aux paramètres. Les paramètres sont les variables accessibles à la fonction, comme une variable name, tandis que les arguments sont les valeurs réelles que vous transmettez, comme la chaîne "Rover".

Avertissement : Contrairement à d'autres langages comme Java, où une fonction peut modifier la valeur transmise à un paramètre, les paramètres Kotlin sont immuables. Vous ne pouvez pas réattribuer la valeur d'un paramètre à partir du corps de la fonction.

5. Fonctions avec plusieurs paramètres
Vous avez ajouté un paramètre permettant de modifier le message de félicitations en fonction du nom du destinataire. Cependant, vous pouvez également définir plusieurs paramètres pour une fonction, voire même des paramètres avec des types de données différents. Dans cette section, vous modifierez le message de félicitations pour qu'il change aussi en fonction de l'âge du chien.

565f16527e71f507.png

Les définitions des paramètres sont séparées par une virgule. De même, lorsque vous appelez une fonction avec plusieurs paramètres, vous séparez également les arguments transmis par une virgule. Passons à la démonstration !

Après le paramètre name, ajoutez un paramètre age de type Int à la fonction birthdayGreeting(). La nouvelle déclaration de fonction doit comporter les deux paramètres name et age, séparés par une virgule :

fun birthdayGreeting(name: String, age: Int): String {
    val nameGreeting = "Happy Birthday, $name!"
    val ageGreeting = "You are now 5 years old!"
    return "$nameGreeting\n$ageGreeting"
}
La nouvelle chaîne de félicitations doit utiliser le paramètre age. Mettez à jour la fonction birthdayGreeting() pour utiliser la valeur du paramètre age dans la chaîne ageGreeting.

fun birthdayGreeting(name: String, age: Int): String {
    val nameGreeting = "Happy Birthday, $name!"
    val ageGreeting = "You are now $age years old!"
    return "$nameGreeting\n$ageGreeting"
}
Exécutez la fonction et observez les erreurs dans la sortie :

No value passed for parameter 'age'
No value passed for parameter 'age'
Modifiez les deux appels à la fonction birthdayGreeting() dans main() pour transmettre un âge différent pour chaque chien. Transmettez 5 pour l'âge de Rover et 2 pour l'âge de Rex.

fun main() {
    println(birthdayGreeting("Rover", 5))
    println(birthdayGreeting("Rex", 2))
}
Exécutez votre code. Maintenant que vous avez transmis des valeurs pour les deux paramètres, la sortie devrait refléter le nom et l'âge de chaque chien lorsque vous appelez la fonction.

Happy Birthday, Rover!
You are now 5 years old!
Happy Birthday, Rex!
You are now 2 years old!
Signature de la fonction
Jusqu'à présent, vous avez vu comment définir le nom de la fonction, les entrées (paramètres) et les sorties. Le nom de la fonction et ses entrées (paramètres) sont collectivement appelés signatures de la fonction. La signature de la fonction se compose de tout ce qui précède le type renvoyé et figure dans l'extrait de code suivant.


fun birthdayGreeting(name: String, age: Int)
Les paramètres, séparés par une virgule, sont parfois appelés liste de paramètres.

Ces termes figurent souvent dans la documentation pour désigner le code écrit par d'autres développeurs. La signature de la fonction vous indique son nom et les types de données qui peuvent être transmis.

Vous en savez maintenant beaucoup plus sur la syntaxe liée à la définition des fonctions. Le schéma suivant est un récapitulatif de la syntaxe des fonctions.

6. Arguments nommés
Dans les exemples précédents, vous n'avez pas eu besoin de spécifier le nom des paramètres, name ou age, lorsque vous avez appelé une fonction. Cela est toutefois possible si vous le souhaitez. Peut-être voulez-vous, par exemple, appeler une fonction comportant de nombreux paramètres ou transmettre vos arguments dans un ordre différent, par exemple en plaçant le paramètre age avant name. Quand vous incluez le nom du paramètre lorsque vous appelez une fonction, on parle d'argument nommé. Essayez d'utiliser un argument nommé avec la fonction birthdayGreeting().

Modifiez l'appel correspondant à Rex pour qu'il utilise des arguments nommés, comme indiqué dans cet extrait de code. Pour ce faire, incluez le nom du paramètre suivi d'un signe égal, puis de la valeur (par exemple, name = "Rex").

println(birthdayGreeting(name = "Rex", age = 2))
Exécutez le code et observez que la sortie reste la même :

Happy Birthday, Rover!
You are now 5 years old!
Happy Birthday, Rex!
You are now 2 years old!
Réorganisez les arguments nommés. Par exemple, placez l'argument nommé age avant l'argument nommé name.

println(birthdayGreeting(age = 2, name = "Rex"))
Exécutez le code et notez que la sortie reste la même. Même si vous avez modifié l'ordre des arguments, les mêmes valeurs sont transmises pour les mêmes paramètres.

Happy Birthday, Rover!
You are now 5 years old!
Happy Birthday, Rex!
You are now 2 years old!

7. Arguments par défaut
Les paramètres de fonction peuvent également spécifier des arguments par défaut. Peut-être que Rover est votre chien préféré ou peut-être vous attendez-vous simplement à ce qu'une fonction soit appelée avec des arguments spécifiques dans la plupart des cas. Lorsque vous appelez une fonction, vous pouvez choisir d'omettre les arguments associés à une valeur par défaut, auquel cas l'argument par défaut sera utilisé.

Pour ajouter un argument par défaut, insérez l'opérateur d'attribution (=) après le type de données du paramètre, puis définissez-le sur une valeur. Modifiez le code pour utiliser un argument par défaut.

Dans la fonction birthdayGreeting(), définissez le paramètre name sur la valeur par défaut "Rover".

fun birthdayGreeting(name: String = "Rover", age: Int): String {
    return "Happy Birthday, $name! You are now $age years old!"
}
Lors du premier appel à birthdayGreeting() correspondant à Rover dans main(), définissez l'argument nommé age sur 5. Comme le paramètre age est défini après name, vous devez utiliser l'argument nommé age. Sans arguments nommés, Kotlin suppose que les arguments sont dans le même ordre que les paramètres définis. L'argument nommé permet de s'assurer que Kotlin attend un entier (Int) pour le paramètre age.

println(birthdayGreeting(age = 5))
println(birthdayGreeting("Rex", 2))
Exécutez votre code. Le premier appel de la fonction birthdayGreeting() imprime "Rover", car vous n'avez spécifié aucun nom. Le deuxième appel à birthdayGreeting() continue à utiliser la valeur Rex, que vous avez transmise pour l'élément name.

Happy Birthday, Rover! You are now 5 years old!
Happy Birthday, Rex! You are now 2 years old!
Supprimez le nom du deuxième appel à la fonction birthdayGreeting(). Là encore, étant donné que name est omis, vous devez utiliser un argument nommé pour l'âge.

println(birthdayGreeting(age = 5))
println(birthdayGreeting(age = 2))
Exécutez votre code, puis observez que les deux appels à birthdayGreeting() impriment "Rover" comme nom, car aucun argument de nom n'est transmis.

Happy Birthday, Rover! You are now 5 years old!
Happy Birthday, Rover! You are now 2 years old!

8. Conclusion
Félicitations ! Vous savez maintenant définir et appeler des fonctions en Kotlin.

Résumé
Les fonctions sont définies avec le mot clé fun et contiennent des éléments de code réutilisables.
Les fonctions facilitent la gestion des programmes de grande envergure et évitent la répétition inutile de code.
Les fonctions peuvent renvoyer une valeur que vous pouvez stocker dans une variable pour une utilisation ultérieure.
Les fonctions peuvent utiliser des paramètres, qui sont des variables disponibles dans le corps d'une fonction.
Les arguments sont les valeurs que vous transmettez lorsque vous appelez une fonction.
Vous pouvez nommer des arguments lorsque vous appelez une fonction. Lorsque vous utilisez des arguments nommés, vous pouvez les réorganiser sans affecter la sortie.
Vous pouvez spécifier un argument par défaut qui vous permet d'omettre l'argument lorsque vous appelez une fonction.


<!---->

