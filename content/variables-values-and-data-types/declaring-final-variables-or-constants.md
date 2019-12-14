In this section, you will learn how to declare final variables or constants.

A final variable is variable that you can't change after initializing.
The compiler will generate errors if you try to change it. It is also
called as a *constant*.

The basic form of a constant declaration statement is shown here.
```
final type name = expression;
```

The only difference between declaring a variable and a constant is the
use of `final` keyword.

Take a look at this example where two constants are declared.
```
final int NUMBER_OF_MONTHS = 12;
final double PI = 3.142857142857143;
```

We suggest you to use only capital letters for naming constants. It helps you
easily spot constants in your programs.

### Declaring Two or More Constants in One Statement

You can declare two or more constants in a single statement, just like variables.
You must separate the constant names with commas. All the constants will have the
same type.

Here's an example where four constants are declared.
```
int NUMBER_OF_MONTHS = 12,
    NUMBER_OF_DAYS_IN_YEAR = 365,
    NUMBER_OF_DAYS_IN_LEAP_YEAR = 366,
    NUMBER_OF_DAYS_IN_WEEK = 7;
```

Although this is easier, we suggest you to avoid this. Because it makes your
code less easier to read.

### Advantages of Using Constants

Using constants has the following advantages:
* If you later decide to change its value, you must change in just one place.
  You have to change only the initializer.  In case of using a literal, you would have to change everywhere, which is error prone.
* Constants make your programs easier to read.