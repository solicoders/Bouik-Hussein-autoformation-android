3. What is Jetpack Compose?
Jetpack Compose is a modern toolkit for building Android UIs. Compose simplifies and accelerates UI development on Android with less code, powerful tools, and intuitive Kotlin capabilities. With Compose, you can build your UI by defining a set of functions, called composable functions, that take in data and describe UI elements.

Composable functions
Composable functions are the basic building block of a UI in Compose. A composable function:

Describes some part of your UI.
Doesn't return anything.
Takes some input and generates what's shown on the screen.
Annotations
Annotations are means of attaching extra information to code. This information helps tools like the Jetpack Compose compiler, and other developers understand the app's code.

An annotation is applied by prefixing its name (the annotation) with the @ character at the beginning of the declaration you are annotating. Different code elements, including properties, functions, and classes, can be annotated. Later on in the course, you'll learn about classes.

The following diagram is an example of annotated function:

Diagram showing anatomy of a composable function where prefix character @ annotation is composable followed by the function declaration.

The following code snippet has examples of annotated properties. You will be using these in the coming codelabs.


// Example code, do not copy it over

@Json
val imgSrcUrl: String

@Volatile
private var INSTANCE: AppDatabase? = null
Annotations with parameters
Annotations can take parameters. Parameters provide extra information to the tools processing them. The following are some examples of the @Preview annotation with and without parameters.

Android studio screenshot showing code and preview 

Annotation without parameters

Android studio screenshot showing code and preview 

Annotation previewing background

Android studio screenshot showing code and preview 

Annotation with a preview title

You can pass multiple arguments to the annotation, as shown here.


