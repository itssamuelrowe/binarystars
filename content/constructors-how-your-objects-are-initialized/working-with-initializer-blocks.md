+++
title = "Working with Initializer Blocks"
weight = 4
+++

An initializer block is a special block of code which initializes an object.
It is written inside a class and outside methods and constructors. You cannot
assign a name to an initializer block.

The general form of an initializer block is shown here.
```
{
    statement1
    statement2
    ...
    statementN
}
```

It is always executed whenever an instance of a class is created, before any
constructors are invoked. In other words, it does not matter which constructor
you invoke, the initializer block always runs.

You can have more than one initializer in your class. They are run in the order
in which they appear in your source code.

Here is an example which uses an initializer block.

```
class SimpleInteger {

    private int value;

    {
        value = 10;
    }

    public int getValue() {
        return value;
    }

    public void setValue(int value0) {
        value = value0;
    }
}

public class SimpleIntegerExample {

    public static void main(String[] arguments) {
        SimpleInteger i = new SimpleInteger();
        System.out.println("The value stored in i = " + i.getValue());
    }
}
```

You can use constructors or methods as an alternative.

## Static Initializer Blocks

Sometimes you may want to initialize your static fields, or class variables
after computating a value.

Initializer blocks are not executed until an instance of a class is created.
Therefore, you cannot expect to initialize static fields with them.
Because, you may access a class variable before you create an instance of the
class.

Java provides a special type of initializer block known as a static initializer
block. It is executed when the class is loaded. Since you cannot control when
a class is loaded in all cases, we recommend you to design your static initializers
to be unaware of the context in which it is executed.

The general form of a static initializer is shown here.
```
static {
    statement1
    statement2
    ...
    statementN
}
```

As you can see, a static initializer block is similar to an initializer block,
except it begins with the static `keyword`. 

You can have more than one static initializer in your class. They are run in the
order in which they appear in your source code.