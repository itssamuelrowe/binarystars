In Java, errors of all types are generalized into a special type of object
known as an exception.

An *exception* is an object which represents an unexpected event. It occurs when
your program is running. It disturbs the flow of your program. Exceptions are
used to indicate many types of error conditions. 

An exception is represented by an object. It holds the information about the
event such as the condition, the stacktrace, the location, and a message.

The exception object is usually refered to as *exception*. You can *throw and
catch* an exception.

After an exception object is created, it is thrown. The Java Virtual Machine
attempts to find an exception handler for the exception by backtracking the list
of methods that have been called, known as the call stack. If a handler is found,
the exception is caught.

An exception may occur for many reasons. For example, the programmers did not
anticipate possible problems, or the application is untested, or the program
encounters situations such as corrupt data, corrupt files, network problems,
hardware device failure, and so on.

Here are some common exceptions.
    * `OutOfMemoryError`
    * `StackOverflowError`
    * `FileNotFoundException`
    * `IOException`
    * `NullPointerException`
    * `ArrayIndexOutOfBoundsException`

When an unexpected situation occurs, an exception object is created and *thrown*.
The method which invoked the current method can handle the exception or
let it pass through. At some point, the exception is caught and handled.
Exceptions can be thrown either by your code, or the Java Virtual Machine, or
any libraries your code uses.

Exceptions thrown by the Java Virtual Machine indicate errors that violate the
rules of Java. For example, if you try to access an instance member through a
`null` reference, the JVM throws a `NullPointerException`.

Exception handling in Java uses the following keywords.
    * `try`
    * `catch`
    * `throw`
    * `throws`
    * `finally`

In short, when an exception occurs, a new exception object is created.
This object is thrown using a throw statement. Your code can anticipate exceptions
to be thrown from a block of code using the `try` clause. If an exception is
thrown within the `try` block your code is monitoring, your code can handle this
exception using the `catch` clause.

Generally, if your method throws an exception you need to mark it with the `throws`
clause. Any code that must be executed regardless of an exception being thrown
or not, must be written in the `finally` clause.

Here is the general form of a try statement.
```
try {
    statement1
    statement2
    ...
    statementN
}
catch (Exception1 exception) {
    // Handle the exception `Exception1`
}
catch (Exception2 exception) {
    // Handle the exception `Exception2`
}
finally {
    statementA
    statementB
    ...
    statementK
}
```

Here, `Exception1` and `Exception2` indicate the type of exception to catch.
You will learn more about the mechanics involved throughout this chapter.