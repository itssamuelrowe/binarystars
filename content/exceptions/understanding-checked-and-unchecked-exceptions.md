+++
title = "Understanding Checked and Unchecked Exceptions"
weight = 6
+++

An *unchecked exception* is an exception which you can handle if you want.
Any exception class which inherits the *RuntimeException* class is an unchecked
exception. The compiler doesn't force you to handle it. Methods that throw such
exceptions don't have to declare that they throw them. It is assumed that the
application cannot do anything to recover from such exceptions at runtime.
So far, all the exceptions you have used are unchecked exceptions.

A *checked exception* is an exception which you need to handle. Otherwise the
compiler generates errors. Any exception class which inherits the *Exception*
class is a checked exception. When a method throws a checked exception, it has to
declare that it throws such an exception in its declaration using the throws
clause. An example of a checked exception is the `IOException` class.

The general form of the throws clause is shown here.

```
modifiers returnType name(parameters) throws Exception1, Exception2, ..., ExceptionN {
    ...
}
```

You have already learnt all the components involved in a method declaration,
except the throws clause. This clause begins with the `throws` keyword followed
by a list of checked exceptions the method throws. Each checked exception is
separated by a comma. You don't have to specify unchecked exceptions here.

Further, methods that invoke other methods that throw checked exceptions must
either handle them using a try statement or let them propagate by declaring that
using the throws clause. There is a lot of controversy around checked vs.
unchecked exceptions.

Unchecked exceptions allow you to ignore exceptions that you cannot recover
from, and only handle the ones you can. This leads to less clutter. However,
many programmers simply ignore unchecked exceptions. Turning all exceptions
into unchecked exceptions would lead to complicated error handling.