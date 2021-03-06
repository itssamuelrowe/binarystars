+++
title = "Throwing Exceptions"
weight = 5
+++

So far, you have only learnt to catch exceptions. In particular, the exceptions
that were thrown by Java. However, you can throw an exception manually, using
the throw statement.

The general form of throw statement is shown here.
```
throw expression;
```

The throw statement is a simple statement. Therefore, it is terminated by a
semicolon.

Here, the `expression` must evaluates to an object whose type inherits `Throwable`.
It can be an instance of the `Throwable` class itself.

Unlike C++, you cannot throw primitive values such as integer or floating-point
decimals. In fact, you cannot throw an instance of a class which does not inherit 
the `Throwable` class. Which means, you cannot throw objects such as strings
and arrays.

The flow of execution stops immediately after you throw an exception. Any
statements following the throw statement are skipped. The nearest enclosing try
block is checked to see if it has a catch clause that handles the exception.
If it finds a suitable catch clause, then the control is transferred to that
clause. Otherwise, the next enclosing try statement is checked, and this process
repeats until no try statements are found. In such a case, the default exception
handler is triggered. It will print the stack trace and the error message.
After which, the thread in which the exception occurred is terminated.
So far you have learnt to write single threaded programs. Therefore, if your
main thread terminates, your program itself will terminate.

Here is an example program which throws an exception.

````
public class ThrowDemo {
    private static void printGreetings(String name) {
        if (name.equals("Chikka Chikka Slim Shady")) {
            throw new IllegalArgumentException("That hardly sounds like a name.");
        }
        System.out.println("Hi, " + name);
    }
    
    public static void main(String ... arguments) {
        try {
            printGreetings("Chikka Chikka Slim Shady");
        }
        catch (IllegalArgumentException exception) {
            System.out.println("Error: " + exception.getMessage());
        }
    }
}
```

This program generates the following output.

```
Error: That hardly sounds like a name.
```

The `printGreetings()` method validate the name before printing it. It considers
"Chikka Chikka Slim Shady" an invalid name. Therefore, when you specify this name
it throws an exception. The `IllegalArgumentException` class is an in-built Java
class. It is thrown to indicate an illegal argument passed to a method.
You can pass a message to its constructor.

In the `main()` method, we invoke the `printGreetings()` method with `"Chikka
Chikka Slim Shady"` as the name. This causes it to throw an exception. The
main method catches this exception. You can retrieve the message that you
specified to the constructor of the `IllegalArgumentException` with the `getMessage()`
method. The catch clause retrieves the message and prints it on the console.