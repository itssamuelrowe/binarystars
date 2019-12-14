+++
title = "Understanding Methods That Return Value"
weight = 3
+++

Methods that perform operations without returning any value are useful. But this
is not the case always. In this section you will learn how to return values
from methods.

Imagine that you write a method that accepts your date of birth and calculates
your age. Probably the method can print it on the console. But this is not what
you always want. For example, you would want the calculated age to determine if
you are eligible to vote, or not. In such cases, your method needs to return
a value or store the result in some field. Usually, returning a value is much
easier.

To create a method that returns a value, you need to write the type of values
your method returns. The return type of a method can either be a primitive type
or a reference type. When your method does not return any value, you can declare
it as `void`.

Here is an example of a method that accepts a number and determines if it
is even, or not.
```
public class IntegerHelper {

    public static boolean isEven(int number) {
        if ((number % 2) == 0) {
            return true;
        }
        else {
            return false;
        }
    }
    
    public static void main(String... arguments) {
        int n = 19;
        String result = isEven(n) ? "even" : "odd";
        System.out.println(n + " is " + result); 
    }
}
```

Here, the `isEven` method accepts an integer value. It then divides it by 2 for
remainder. If the remainder is `0`, it returns `true` indicating an even number.
Otherwise, it returns `false` indicating an odd number.

Here is another version of the `isEven` method.
```
boolean isEven(int number) {
    return (number % 2) == 0);
}
```

## Using the Return Statement

When you specify a return type other than `void` in your method declaration,
the method must include a return statement. Otherwise, the compiler generates
errors.

Here is the general form of the return statement.

```
return expression;
```

The expression must evaluate to a value which will be returned by the method.
You cannot return more than one value at a time.
The value should be the same type as the type mentioned in the declaration
of the method. In other words, if the method returns a `String`, the expression
in the return statement cannot evaluate to an integer.

Further, the method terminates as soon the return statement is executed. Improper
use of return statements create unreachable regions in your method causing bugs.
In fact, we recommend you to design your methods to always use a minimum number
of return statements. This way you can easily determine the exit points of your
method.

Void methods can use the return statement, but it must not return anything.
In other words, void methods can simply use the `return` keyword without any
expression for terminating the method.

Also, the compiler is smart enough to complain if you try to trick it
without returning a value.

Here is an example of the `isEven` method. This code segement would generate
an error.

```
boolean isEven(int number) {
    if ((number % 2) == 0)) {
        return true;
    }
}
```

In this example, the method does not return a value in all cases. If the specified
number was odd, the method would not return any value. But the compiler expects
you to return a value in all cases. This is why it would generate errors if you
tried to feed code like this.

You should be careful when you return values from loops and conditional statements.
You need to ensure that a value is returned in all case.

Here is an example of a program that computes the factorial of a number.
```
public class Factorial {

	private int compute(int number) {
		int result = 1;
		for (int i = 2; i <= number; i++) {
			result = result * i;
		}
		return result;
	}

	public static void main(String[] arguments) {
		Factorial factorial = new Factorial();
		int result = factorial.compute(5);

		System.out.println("5! = " + result);
	}
}
```