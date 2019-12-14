+++
title = "Using the Finally Clause"
weight = 7
+++

When an exception is thrown, the execution of your code jumps abruptly, possibly
from one method to another method. This means some important segment of your
code may be skipped. This could be a problem in some methods.

For example, if a method opens a file in the beginning and closes it before
returning, then you will not want the code that closes the file to be skipped
by an exception. The finally clause is designed to control such situations.

You can create a finally clause in a try statement. The finally clause is
basically a block of code that will always be executed, regardless of an exception
being thrown or not. If an exception is thrown, the finally block will execute
even if no catch clause matches.

If a method is returns to the caller from inside a try/catch clauses, via an
uncaught exception or a return statement, the finally clause is executed just
before the method returns.

The finally clause is optional. However, a try clause requires least one catch
or a finally clause to follow it.

```
public class FinallyDemo {

    private static int divide(int a, int b) {
        return a / b;
    }
    
    public static void main(String... arguments) {
        int a = 7;
        int b = 0;
        try {
            int c = divide(a, b);
            System.out.println(c);
        }
        finally {
            System.out.println("This statement was executed.");
        }
    }
}
```

This example generates the following output.

```
This statement was executed.
Exception in thread "main" java.lang.ArithmeticException: / by zero
        at FinallyDemo.divide(FinallyDemo.java:4)
        at FinallyDemo.main(FinallyDemo.java:11)
```

As you can see, the `println` statement inside the finally clause was executed
even when an exception was thrown. Without the finally clause the exception
would have prevented the `println` statement from being executed.