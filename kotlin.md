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


6. Change font size
You added text to your user interface, but it doesn't look like the final app yet. In this task, you learn how to change the size, text color, and other attributes that affect the appearance of the text element. You can also experiment with different font sizes and colors.

Scalable pixels
The scalable pixels (SP) is a unit of measure for the font size. UI elements in Android apps use two different units of measurement: density-independent pixels (DP), which you use later for the layout, and scalable pixels (SP). By default, the SP unit is the same size as the DP unit, but it resizes based on the user's preferred text size under phone settings.

In the MainActivity.kt file, scroll to the Text() composable in the GreetingText() function.
Pass the Text() function a fontSize argument as a second named argument and set it to a value of 100.sp.

Text(
    text = message,
    fontSize = 100.sp
)
Android Studio highlights the .sp code because you need to import some classes or properties to compile your app.

8032c2d4926903d5.png

Click .sp, which is highlighted by Android Studio.
Click Import in the popup to import the androidx.compose.ui.unit.sp to use the .sp extension property.
Note: The AndroidX (Android Extension) library contains a set of libraries and classes that help accelerate your app development, by providing you the core functionality. You can access the classes, properties, and other artifacts using the androidx package.

Scroll to the top of the file and notice the import statements, where you should see an import androidx.compose.ui.unit.sp statement, which means that Android Studio adds the package to your file.
e073e9d3465e080c.png

Note: If you encounter any problems with importing using Android Studio, you can manually add the imports at the top of the file.

Notice the updated preview of the font size. The reason for overlapping message is you need to specify the line height.
b001a2c51b985d0.png

Note: The sp is an extension property for Int, which creates an sp unit. Similarly, you can use the .sp extension property in other data types, like Float and Double.

Update the Text composable to include the line height.

@Composable
fun GreetingText(message: String, modifier: Modifier = Modifier) {
    Text(
        text = message,
        fontSize = 100.sp,
        lineHeight = 116.sp,
    )
}
cefc09e773d1f29a.png

Now you can experiment with different font sizes.

8. Arrange the text elements in a row and column
UI Hierarchy
The UI hierarchy is based on containment, meaning one component can contain one or more components, and the terms parent and child are sometimes used. The context here is that the parent UI elements contain children UI elements, which in turn can contain children UI elements. In this section, you will learn about Column, Row, and Box composables, which can act as parent UI elements.

9270b7e10f954dcb.png

The three basic, standard layout elements in Compose are Column, Row, and Box composables. You learn more about the Box composable in the next codelab.

column showing three elements  arranged vertically and a row showing three elements arranged horizontally 

Column, Row, and Box are composable functions that take composable content as arguments, so you can place items inside these layout elements. For example, each child element inside a Row composable is placed horizontally next to each other in a row.


// Don't copy.
Row {
    Text("First Column")
    Text("Second Column")
}
These text elements display next to each other on the screen as seen in this image.

The blue borders are only for demonstration purposes and don't display.

7117f9998760a828.png

Trailing lambda syntax
Notice in the previous code snippet that curly braces are used instead of parentheses in the Row composable function. This is called Trailing Lambda Syntax. You learn about lambdas and trailing lambda syntax in detail later in the course. For now, get familiar with this commonly used Compose syntax.

Kotlin offers a special syntax for passing functions as parameters to functions, when the last parameter is a function.

function parameter is the last parameter

When you pass a function as that parameter, you can use trailing lambda syntax. Instead of putting the function inside the parentheses, you can place it outside the parentheses in curly braces. This is a recommended and common practice in Compose, so you need to be familiar with how the code looks.

For example, the last parameter in the Row() composable function is the content parameter, a function that describes the child UI elements. Suppose you wanted to create a row that contains three text elements. This code would work, but it's very cumbersome to use named parameter for the trailing lambda:


Row(
    content = {
        Text("Some text")
        Text("Some more text")
        Text("Last text")
    }
)
Because the content parameter is the last one in the function signature and you pass its value as a lambda expression (for now, it's okay if you don't know what a lambda is, just familiarize yourself with the syntax), you can remove the content parameter and the parentheses as follows:


Row {
    Text("Some text")
    Text("Some more text")
    Text("Last text")
}
Arrange the text elements in a row
In this task, you arrange the text elements in your app in a row to avoid overlap.

In the MainActivity.kt file, scroll to the GreetingText() function.
Add the Row composable around the text elements so that it shows a row with two text elements. Select the two Text composables, click on the light bulb. Select Surround with widget > Surround with Row.
bb8e10def9aa7b7e.png

ca2ff1086fb0802c.png

Now the function should look like this code snippet:


@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Row {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp,
        )
        Text(
            text = from,
            fontSize = 36.sp
        )
    }
}
Android Studio auto imports Row function for you. Scroll to the top and notice the import section. The import androidx.compose.foundation.layout.Row should have been added.
Observe the updated preview in the Design pane. Temporarily change the font size for the birthday message to 30.sp.
Birthday greeting and signature are displayed next to each other in a row.

The preview looks much better now that there's no overlap. However, this isn't what you want because there's not enough room for your signature. In your next task, you arrange the text elements in a column to resolve this issue.

Arrange the text elements in a column
In this task, it is your turn to change the GreetingText() function to arrange the text elements in a column. The preview should look like this screenshot:

785f6c6e087b03b.png

Now that you've tried doing this on your own, feel free to check your code against the solution code in this snippet:


@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp
        )
        Text(
            text = from,
            fontSize = 36.sp
        )
    }
}
Notice the auto imported package by Android Studio:


import androidx.compose.foundation.layout.Column
Recollect that you need to pass the modifier parameter to the child element in the composables. That means you need to pass the modifier parameter to the Column composable.


@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(modifier = modifier) {
        Text(
            text = message,
            fontSize = 100.sp,
            lineHeight = 116.sp
        )
        Text(
            text = from,
            fontSize = 36.sp
        )
    }
}
9. Add greeting to the app
Once you're happy with the preview, it's time to add the composable to your app on your device or emulator.

In the MainActivity.kt file, scroll to the onCreate() function.
Call the GreetingText() function from the Surface block.
Pass the GreetingText() function, your birthday greeting and signature.
The completed onCreate() function should look like this code snippet:


class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            HappyBirthdayTheme {
                // A surface container using the 'background' color from the theme
                Surface(
                    modifier = Modifier.fillMaxSize(),
                    color = MaterialTheme.colorScheme.background
                ) {
                    GreetingText(message = "Happy Birthday Sam!", from = "From Emma")
                }
            }
        }
    }
}
Build and run your app on the emulator.
433859d648d9b26.png

Align greeting to the center
To align the greeting in the center of the screen add a parameter called verticalArrangement set it to Arrangement.Center. You will learn more on the verticalArrangement in a later codelab.

@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(
        verticalArrangement = Arrangement.Center,
        modifier = modifier
    ) {
        // ...
    }
}
Add 8.dp padding around the column. It is a good practice to use padding values in increments of 4.dp.

@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(
        verticalArrangement = Arrangement.Center,
        modifier = modifier.padding(8.dp)
    ) {
        // ...
    }
}
To further beautify your app, align the greeting text to the center using textAlign.

Text(
    text = message,
    fontSize = 100.sp,
    lineHeight = 116.sp,
    textAlign = TextAlign.Center
)
ac614110dd73da93.png

In the above screenshot, only the greeting is center aligned because of the textAlign parameter. The signature, From Emma has the default alignment which is left.

Add padding to the signature and align it to the right.

Text(
    text = from,
    fontSize = 36.sp,
    modifier = Modifier
        .padding(16.dp)
        .align(alignment = Alignment.End)
)
4c8c1e27bc2f6869.png

Adopt good practice
It is a good practice to pass the modifier attribute(s) along with the modifier from the parent composable. Update the modifier parameter in the GreetingText() as follows:

onCreate()


Surface(
    //...
) {
    GreetingText(
        message = "Happy Birthday Sam!",
        from = "From Emma",
        modifier = Modifier.padding(8.dp)
    )
}
GreetingText()


@Composable
fun GreetingText(message: String, from: String, modifier: Modifier = Modifier) {
    Column(
        verticalArrangement = Arrangement.Center,
        modifier = modifier
    ) {
        // ...
    }
}
Build and run your app on the emulator to see the final result.

3. Add an Image composable
To display an image in your app, it needs a place to be displayed. Just like you use a Text composable to display text, you can use an Image composable to display an image.

In this task, you add an Image composable to your app, set its image to the image that you downloaded, position it and adjust its size so that it fills the screen.

Add a composable function to add an image
In the MainActivity.kt file, add a GreetingImage() composable function after the GreetingText() function.
Pass the GreetingImage() function two String parameters: one called message for the birthday greeting and the other called from for your signature.

@Composable
fun GreetingImage(message: String, from: String) {
}
Every composable function should accept an optional Modifier parameter. Modifiers tell a UI element how to lay out, display, or behave within its parent layout. Add another parameter at the GreetingImage() composable.

@Composable
fun GreetingImage(message: String, from: String, modifier: Modifier = Modifier) {
}
Resources in Jetpack Compose
Resources are the additional files and static content that your code uses, such as bitmaps, user-interface strings, animation instructions, and more. For more information about resources in Android, see App resources overview.

You should always separate app resources, such as images and strings, from your code so that you can maintain them independently. At runtime, Android uses the appropriate resource based on the current configuration. For example, you might want to provide a different UI layout based on the screen size or different strings based on the language setting.

Grouping resources
You should always place each type of resource in a specific subdirectory of your project's res/ directory. For example, here's the file hierarchy for a simple project:


MyProject/
    src/
        MyActivity.kt
    res/
        drawable/
            graphic.png
        mipmap/
            icon.png
        values/
            strings.xml
As you can see in this example, the res/ directory contains all the resources in subdirectories, which includes a drawable/ directory for an image resource, a mipmap/ directory for launcher icons, and a values/ directory for string resources. To learn more about the usage, format, and syntax for app resources, see Resource types overview.

Accessing resources
Jetpack Compose can access the resources defined in your Android project. Resources can be accessed with resource IDs that are generated in your project's R class.

An R class is an automatically generated class by Android that contains the IDs of all resources in the project. In most cases, the resource ID is the same as the filename. For example, the image in the previous file hierarchy can be accessed with this code:


R.drawable.graphic
R is a autogenerated class drawable is a sub directory in res folder graphic is resource ID

In the next task, you use the image, androidparty.png file, which you added in the previous task.

In the GreetingImage() function, declare a val property and name it image.
Make a call to painterResource() function by passing in the androidparty resource. Assign the returned value to the image variable.

val image = painterResource(R.drawable.androidparty)
Android Studio highlights the .painterResource code because you need to import the function to compile your app.

82323978341a0bdc.png

Click .painterResource, which is highlighted by Android Studio.
Click Import in the popup to add the import for androidx.compose.ui.res.painterResource.
The painterResource() function loads a drawable image resource,and takes resource ID (R.drawable.androidparty in this case) as an argument.

After the call to the painterResource() function, add an Image composable and then pass in the image as a named argument for the painter.

Image(
    painter = image
)
Android Studio highlights the Image code because you need to import the function to compile your app.

e2bead11643e0577.png

To fix this warning, add the following import at the top of your MainActivity.kt file:


import androidx.compose.foundation.Image
The initial warning is now resolved but if you hover over the word Image, Android Studio displays a new warning that states, "None of the following functions can be called with the arguments supplied." This is because the provided argument does not match any of the Image function signatures.

bf100321c787e042.png

This warning will be fixed in the next section.

Check your app for accessibility
When you follow coding practices for accessibility, you let all of your users, including those with disabilities, more easily navigate, and interact with, your app.

Note: Android provides many tools for users. For example, TalkBack is the Google screen reader included on Android devices. TalkBack gives users spoken feedback so that users can use their device without looking at the screen. To learn more about accessibility, see Build accessible apps.

Android Studio provides hints and warnings to help you make your app more accessible. A content description defines the purpose of a UI element, which makes your app more usable with TalkBack.

However, the image in this app is only included for decorative purposes. The addition of a content description for the image would make it harder to use with TalkBack in this particular case. Instead of setting the content description that's announced to the user, you can set the image's contentDescription argument to null so that TalkBack skips the Image composable.

In the Image composable, add another named argument called contentDescription and set its value to null.

Image(
    painter = image,
    contentDescription = null
)
Preview the Image composable
In this task, you preview the image composable and run the app on an emulator or device.

In the BirthdayCardPreview() function, replace the GreetingText() function call with a GreetingImage() function call.
Your function should look like this code snippet:


@Preview(showBackground = true)
@Composable
fun BirthdayCardPreview() {
    HappyBirthdayTheme {
        GreetingImage(
            message = "Happy Birthday Sam!",
            from = "From Emma"
        )
    }
}
The Design pane should auto update, if it doesn't, click 609ccb451d05cf6b.png to build.
Notice that you can't see the text anymore because the new function only has an Image composable, but not a Text composable.

acd47e25eb2a8d55.png