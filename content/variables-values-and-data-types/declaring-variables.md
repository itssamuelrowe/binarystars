In this lecture, you will learn how to declare variables.

You must *declare* a variable before using it. The compiler will display
errors otherwise.

The basic form of a variable declaration statement is shown below.
```
type name;
```

A variable name is an identifier. You can refer the value stored in the 
variable with its name.

The type indicates the values that can be stored in a variable.

Notice that a variable declaration ends with a semicolon. That is because the
variable declaration statement is a simple statement.

Here's an example where two variables are declared.
```
String name;
int age;
```

In this example, you *declared* variables named `name` and `age`. The variable
`name` can hold string values. The variable `age` can hold integer values.

You will learn more about *data types* in the next lecture. Until then remember
that `int` variables can hold integer values. In other words, `int` variables can
hold whole numbers like `1`, `20000`, and `100`. `String` variables can hold
text values such as `"Hello"`, `"Samuel Rowe"`, and `"Shazam"`.

### Declaring Two or More Variables in One Statement

You can declare two or more variables in a single statement. You must separate
the variable names with commas. All the variables will have the same type.

Here's an example where four variables are declared.
```
int a, b, c, d;
```

Although this is easier, we suggest you to avoid this. Because it makes your
code less easier to read.

### Understanding Local Variables

A local variable is a variable that you declare within the body of a method.
You can use a local variable only within that method. You can't use it outside
the method.

For example, the variable `k` exists only with the braces of the `main` method.
```
public class Example {

    public static void main(String[] arguments) {
        int k;
        
        /* You can refer 'k' only within the braces of this method. */
    }
}
```

The region in which your variable exists is known as *scope*. You will learn
more about scopes later in the course.

The place where you declare a local variable is important. You must declare
a variable before you use it.

For example, the compiler generates an error if you try to compile this example.
**Because it declares the variable after using it.**

```
public class Example {

    public static void main(String[] arguments) {
        i = 10;
        int i;
    }
}
```

Don't worry if you don't understand what `i = 10` means. You'll learn about it
in the next section.

### Initializing Variables

When you refer the value *stored in a local variable*, the compiler checks if
you assigned a value previously.

For example, the compiler generates an error if you try to compile this
example. **Because it uses a variable without assigning a value.**
```
public class Example {

    public static void main(String[] arguments) {
        String name;
        System.out.println(name);
    }
}
```

To avoid such errors, you must initialize local variables before you use them.
You can assign a variable with an *expression statement*. In particular, you use
the *assignment expression* to assign a variable. You will learn more about
expressions later in the course.

The basic form of an assignment expression is shown here.
```
variable = expression
```

Here, `expression` can be any expression that evaluates to a value.

For example, this is the correct version of the previous example.
```
public class Example {

    public static void main(String[] arguments) {
        String name;
        name = "Samuel Rowe";
        System.out.println(name);
    }
}
```

In this example, the variable is assigned a value of "Samuel Rowe" before
printing it.

### Initializing Variables with Initializers

You can initialize a variable when you declare it. You use an *initializer* to
do this. The general form of an initializer is shown here.
```
type name = expression;
```

The initializer allows you to combine declaration and initialization.

Take a look at some examples given below.

```
String name = "Samuel Rowe";
int age = 19;
float gravity = 9.8f;
double pi = 3.142857142857143;
```

In each of these statements, a variable is declared and initialized.