+++
title = "Understanding Data Types"
weight = 5
+++

Java is *statically typed*. What this means is, the compiler knows the type of
every variable. Once you declare a variable of a certain type, it cannot hold
values of other types.

The advantage of statically typed language is that many *bugs* can be caught
during compilation.

As a Java programmer, you must specify the type of each variable. All the
variables, values, and their types are checked for correctness. The compiler
checks if you assigned the wrong type of data to variables.

Here's an example where a string value is assigned to an integer variable.
Do you think it will compile?
```
public class Example {

    public static void main(String[] arguments) {
        int age = "19";
        System.out.println(age);
    }
}
```

The compiler generates an error if you try to compile this. Because `age` is
declared as a variable of type `int`. An `int` variable can store only integers.
But we tried to assign a string to an `int` variable.

### Different Categories of Data Types

In Java, there are two categories of data types.
    * Primitive Types
    * Reference Types

The *primitive types* are the most basic data types available. They are
**defined by Java**.

The *reference types* are the data types that are **defined by classes, interfaces, and enumerations**.