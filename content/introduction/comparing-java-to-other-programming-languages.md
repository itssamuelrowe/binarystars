+++
title = "Comparing Java to Other Programming Languages"
weight = 5
+++

In this section, we will compare Java to C and C++. We'll learn about their differences.

## Paradigm

Both Java and C++ are Object-Oriented Programming (OOP) languages. Whereas,
C is Procedural Oriented Programming (POP) language.

## Memory Management

All programming languages let you handle data. When you create a variable,
you can assign a portion of the computer’s memory to store the data.
The allocation of memory is a detail that you can usually ignore.
But you need to know what happens to that memory when you no longer need
the data that was stored in it.

In C, C++ and other similar languages, you have to manually release the memory so that
other programs can use it. If you don't, your program develops a memory leak,
which means that your program slowly runs out of memory.

In Java, you don’t have to manually release memory when you’re done with it.
Instead, memory is released automatically when it is no longer needed.

The Java Virtual Machine includes a garbage collector that scans the memory,
determines when data is no longer needed, and automatically releases it.

## Exceptions

No matter how carefully you design and test your programs, errors happen.
When they do, chances are your program crashes to a halt.

In Java, errors of all types are generalized into a special type of object
known as an exception. Java requires any statements that can potentially raise
an exception to be handled. In other words, your program must anticipate
errors that can happen while your program is running. This helps your programs
be more reliable.

C++ has a similar approach to handling exceptions. But then, it is not as
sophisticated as the exception handling mechanism found in Java.

In the case of C, there is no concept of exceptions. Alternatively, you can
use jump buffers. This mechanism is usually frowned upon and most programmers
tend to stay away from it.

These are some of the major differences between Java, C, and C++.

Here's a list of many other differences. Unfortunately, we won't be discussing
all of them in this section.

|                      | C                              | C++                         | Java                        |
|----------------------|--------------------------------|-----------------------------|-----------------------------|
| Creator              | Dennis Ritchie                 | Bjarne Stroustrup           | James Gosling               |
| Year                 | 1972                           | 1979                        | 1995                        |
| Compiled             | Yes                            | Yes                         | Yes                         |
| Interpreted          | No                             | No                          | Yes                         |
| Paradigm             | Procedure Oriented Programming | Object Oriented Programming | Object Oriented Programming |
| Pointers             | Yes                            | Yes                         | No                          |
| Memory Management    | Manual                         | Manual                      | Automatic                   |
| Statically Typed     | Yes                            | Yes                         | Yes                         |
| Preprocessor         | Yes                            | Yes                         | No                          |
| Exceptions           | No                             | Yes                         | Yes                         |
| Function Overloading | No                             | Yes                         | Yes                         |
| Operator Overloading | No                             | Yes                         | No                          |