+++
title = "Working with Strings"
weight = 8
+++

In this section, you will learn the basics of strings.

A string is a sequence of characters. String literals are enclosed in double
quotes (`"`).

Here's an example of a string.
```
"Hello, world!"
```

In Java, string is not a primitive type. It is a reference type. It is
implemented by the `String` class.

Even though `String` is a reference type, it is treated specially.
We take an entire chapter to explain strings. Here, we teach you the
basics. It will help you understand upcoming examples.

### Declaring Strings

Strings are declared like any reference type. Here's an example.
```
String title;
```
Here, we declared a variable named `title`. It can store a reference to
a `String` object.


### Initializing Strings

Unlike other reference type variables, strings are initialized like primitive
types.

Remember `String` isn't a keyword. It's a class defined by the Java API.

Here's an example of initializing a `String` variable.
```
String message;
message = "How are you?";
```

Here, we declared a variable named `message` of type `String`. We initialized
it to `"How are you?"`. Remember that string literals are enclosed in double
quotes (`"`), not in single quotes. Single quotes are used for character literals.

You can combine declaration and initialization like this.
```
String message = "How are you?";
```

To initialize a local string variable to an empty string, use a statement like
this.
```
String string = "";
```

You know that Java is case sensitive. Which means, `String` with uppercase S and `string` with lowercase are
different.

### Joining Strings

You can join two strings by using the *concatenation operator* (`+`).
*Concatenation* means joining two strings.

Here's an example where two strings are joined.
```
public class JoiningStrings {

    public static void main(String[] arguments) {
        String hello = "Hello, ";
        String world = "world!";
        String message = hello + world;

        System.out.println(message);
    }
}
```

When you join strings, no extra characters are added by Java. This includes any
blank spaces between strings. If you want to combine two strings with a space in
between them, you've to do it. In the previous example, the first string ends
with a space.

Here's another example where two strings are joined with and without space in
between them.
```
public class JoiningStringsWithSpace {

    public static void main(String[] arguments) {
        String hello = "Hello,";
        String world = "world!";
        String message1 = hello + " " + world;
        String message2 = hello + world;

        System.out.println(message1);
        System.out.println(message2);
    }
}
```

You can join a string with any primitive type, such as `int` and `float`.
Java converts the primitive value to a string and then joins it.

Here's an example where a string is joined with a `boolean` value.
```
public class JoiningStringsWithPrimitiveValues {

    public static void main(String[] arguments) {
        String question = "Are you Batman?";
        boolean answer = true;
        String message = question + " " + answer;
        System.out.println(message);
    }
}
```

Here we declared a `String` variable named `question`. It holds a simple
question. We declared `boolean` variable named `answer`. It holds `true`.
We joined `question` and `answer` using the concatenation operator (`+`).
The result was stored in `message`. We have added a blank space to seperate
the question and answer. Finally, we printed the string stored in `message`.

### Converting Strings to Primitives

You can convert a string into a primitive value. For example, you can convert the string
`"27"` written with digits into a primitive value. But you can't convert the string "twenty seven"` written in words into an
integer.

You can use one of the following *methods* to convert a string to a primitive
value.

You will learn more about methods later in the book.

| Wrapper Class | Method       |
|---------------|--------------|
| Boolean       | parseBoolean |
| Character     | --           |
| Byte          | parseByte    |
| Short         | parseShort   |
| Integer       | parseInt     |
| Long          | parseLong    |
| Float         | parseFloat   |
| Double        | parseDouble  |

Here's an example of converting strings to primitive values.
```
boolean value1 = Boolean.parseBoolean("true");
byte value2 = Byte.parseByte("27");
short value = Short.parseByte("519");
int value = Integer.parseInt("2000");
long value = Long.parseLong("1999");
float value = Float.parseFloat("5.19");
double value = Double.parseDouble("9.21");
```