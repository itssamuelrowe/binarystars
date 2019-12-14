+++
title = "The Hello World Program"
weight = 1
+++

In this section, you will learn to write the *Hello World* program.

Many programming courses begin with a simple example program that prints the text,
"Hello, world!" on the console.

```
public class Hello {

    public static void main(String... arguments) {
        System.out.println("Hello, world!");
    }
}
```

* Copy the source code from here.
* Paste the source code into a text editor, such as Notepad or Notepad++.
* Save it in a file named *Hello.java*.
* You need to remember where you save your file. In our example, I have saved it
  in `C:\examples\chapter-3`.
* Open a console window.
* Change the current working directory to the directory where your file is
   saved. In our example, it is `C:\examples\chapter-3`.
* To change the current working directory use the `cd` command. For example,
```
cd C:\examples\chapter-3
```
* Compile it with `javac Hello.java` in the console window.
* Run your program with `java Hello` in the console window.

## Opening Console Window on Windows

### Method 1

1. Press the `Windows + R` keys.
2. A dialog with the title `Run` will appear on the screen.
3. Type `cmd` in the text field.
4. Press enter.

### Method 2

1. Click on the Windows logo in the bottom left corner of your screen.
2. Search `cmd.exe` in the search field.
3. Click on `cmd.exe`.

```
public class Hello {
```

Here you created a class called `Hello`. It is public, which means other classes
can access it. You don't have to know what this means for now, so don't
worry. You will learn about *access specifiers* later in the course.

When you declare a public class, you must always save it inside a file with
the same name. In our first example, our class was named `Hello`. So, it was
saved in the file `Hello.java`.

The opening brace `{` begins the body of the class. The end of the body is
marked by the closing brace `}`. Whatever you *declare* within these braces
belongs to the class.

```
    public static void main(String[] arguments) {
```

Here you created a *method* called `main`. You don't have to know what this
means for now, so don't worry. You will learn more about methods later in
the course.

The `main` method is the **entry point** of your Java program. In other words,
your program always starts at `main`.

When you declare a public method, other classes can access it. You will learn
more about **access specifiers** later in the course.

You can *call* a static method without creating an *instance* of `Hello`. You
will learn more about *static* later in the course.

`(String[] arguments)` is too advanced to explain just yet. It’s called a
*parameter list*. You can use it to pass data to a method.

The `main` method always receives a single parameter: an *array* of `String`
objects. If you don’t know what a parameter, a `String`, or an array is, don’t
worry. You will learn more about these concepts later in the course.

The opening brace `{` begins the *body* of the method. The end of the method is
marked by the closing brace `}`. Whatever *statements* you write within these
braces are executed when you call the method.

```
        System.out.println("Hello, World!");
```

`System` is a class that Java provides us. It has some useful methods and
variables. `out` is a *static variable* within `System`. `println` is a
method within `out`. You can call it to write data on your console window.