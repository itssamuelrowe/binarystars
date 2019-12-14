The *primitive types* are the most basic data types available. They are
**defined by Java**.

There are eight primitive data types in Java.
    * `boolean`
    * `char`
    * `byte`
    * `short`
    * `int`
    * `long`
    * `float`
    * `double`

| Type     | Default  | Size    | Range                                                   | Example                                        |
|----------|----------|---------|---------------------------------------------------------|------------------------------------------------|
| boolean  | false    | 1 byte  | true or false                                           | true, false                                    |
| char     | '\u0000' | 2 bytes | 0 to 65,536 (unsigned)                                  | 's', 'M', 'a', 'o', 'H', '7', 'L'              |
| byte     | 0        | 1 byte  | -128 to 127                                             | 5, 2, 7, 19, 100                               |
| short    | 0        | 2 bytes | -32,768 to 32,767                                       | 2000, 2, 7, 19, 5, 1999                        |
| int      | 0        | 4 bytes | -2,147,483,648 to 2,147,483,647                         | 1, 88234, -9991, 22234                         |
| long     | 0        | 8 bytes | -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 | 922337203685477L, -72202593477L, 882200333466L |
| float    | 0.0      | 4 bytes |                                                         | 123.4f, 3.14_15F                               |
| double   | 0.0      | 8 bytes |                                                         | 3.141592653589793d, 1.23456e300d               |

### Working with Boolean

The `boolean` type has two values: `true` or `false`. You can perform *logical
operations* with boolean values. You'll learn more about logical operations later
in the course.

Here's an example of the `boolean` type.
```
boolean initialized = true;
boolean valid = false;
```

In the above example, we declared a `boolean` variable named `initialized` and
assigned it `true`. We also declared another boolean variable named `valid`
and assigned it `false`.

In C and C++, integer values can be used as boolean values, with `0` as `false`
and any other value as `true`. Remember that in Java integers can't be used as
boolean values without *explicit casting*.

You will learn more about explicit casting later in the course.

### Working with Integer Types

An *integer* is a number without any fractional or decimal portion.

There are four integer types you can use.
   * `byte`
   * `short`
   * `int`
   * `long`

You can store different *range* of integer values in each of these types. Because they
differ in size.

The most commonly used integer type is `int`. It uses four bytes (32 bits) to
store an integer value.

If you have read the previous chapters, you have already seen `int` in some
examples. Let's take a look at another example.

```
public class Cars {

    public static void main(String[] arguments) {
        int cars = 100;
        System.out.println(cars);
    }
}
```

If you want to store numbers greater than 2 billion, you can use `long`. It uses
eight bytes (64 bits) to store an integer value.

All integer literals are of type `int` by default. What would you do if you
wanted to assign a huge number like this `1234567890987` to a `long` variable? You must add `L` like this
`1234567890987L`.

Here's an example where we try to assign a `long` variable.
```
public class HugeNumber {

    public static void main(String[] arguments) {
        long number = 2720001951999;
        System.out.println(number);
    }
}
```

If you try to compile it, the compiler will generate errors.
```
HugeNumber.java:4: error: integer number too large: 1234567890987
        long number = 2720001951999;
                      ^
1 error
```

This is the correct version of the previous example. This program will compile
without any errors.
```
public class HugeNumber2 {

    public static void main(String[] arguments) {
        long number = 2720001951999L;
        System.out.println(number);
    }
}
```

You can either use uppercase`L` or lowercase `l`. We suggest you to use uppercase`L`. Because lowercase`l` is confused
with `1` many times.

The `short` and `byte` types use less memory than `int` and `long` types.
They are not used commonly. Because saving a few bytes here or there doesn't
make any difference in performance. You will learn more about saving memory with
`byte` and `short` when you learn about *arrays*.

In C and C++, the size of an integer data type depends on your compiler and
environment. For example, the size of `int` may be four bytes in your computer.
But it may be two bytes in your friends computer. This causes many problems.

This problem has been solved in Java. Because the language decides the sizes of
the integer data types. They don't depend on your compiler or environment.
This way, the sizes remain same on all computers.

### Working with Decimal Types

Decimal numbers are numbers that have fractional parts.

Decimal numbers are stored in *exponential notation*. It is also known as
scientific notation. It has two parts: a base value and an exponent. The base
value is also known as mantissa.

The actual value of a decimal number is calculated by multiplying its mantissa
by two raised to its exponent. Here's the mathematical formula.
```
mantissa × (2 ^ exponent)
```

There are two decimal types you can use.
    * `float`
    * `double`

The most commonly used decimal type is `double`. It uses eight bytes (64 bits)
to store decimal values. *It implements the IEEE 754 double-precision format.*
For `double`, the exponent ranges from -1023 to +1024.

The `float` type uses four bytes (32 bits) to store decimal values. *It implements
the IEEE 754 single-precision format.* For `float`, the exponent ranges from
–127 to +128.

You must add a suffix `D` or `d` to indicate that the literal is of `double` type.
It is optional. Because all decimal literals are of type `double` by default.

What would you do if you wanted to assign `2.7` to a `float` variable? You must add
a suffix uppercase`F` or lowercase`f` to indicate that the literal is of `float` type.

Here's an example.
```
public class AreaOfCircle {

    public static void main(String[] arguments) { 
        float r = 2.7f; 
        double pi = 22.0 / 7.0;
        System.out.println(pi * r * r);
    }
}
```

We suggest you to never use `float` and `double` for precise values, such as
currency.

### Exponents in Decimal Numbers

You can write decimal numbers in scientific notation. Here's a small example.
```
public class Example {

    public static void main(String[] arguments) {
        double n1 = 2.10e+6;
        double n2 = 2100000D;
        System.out.println("n1 = " + n1);
        System.out.println("n2 = " + n2);
    }
}
```

In the above example, both `n1` and `n2` store the same value.

The exponent part either begins with uppercase`E` or lowercase`e`. You can skip the sign if the
exponent is positive.

You could have written `2.10e6` instead of `2.10e+6` in the previous example.

### Working with Characters

The `char` type represents a single *Unicode character*. It uses two bytes (16 bits) to
store a character.

Remeber that a character is not the same as a string. You will learn more about
strings later in this chapter. A character can store just one character. But a
string can store zero or more characters.

You can use a character literal to represent a character. A character literal
is enclosed in single quotes. Whereas, a string is enclosed in double quotes.

Here's an example where we assign character literal to a `char` variable.
```
char n = 'S';
```

Here's another example where we try to assign a string to a `char` variable.
```
public class Example {

    public static void main(String[] arguments) {
        char k = "H"; // Use single quotes to represent characters.
    }
}
```
If you try to compile it, the compiler will generate errors. Because we tried
to assign a string to a `char` variable. A character literal uses single quote (`'`)
not double quotes (`"`).