A lambda expression or closure allows you to create an instance of a functional
interface with the lambda operator (`->`).

A functional interface is any interface that has just one method declaration.
Only such interfaces can be instantiated using the lambda expression.

The general form of a lambda expression is shown here.
```
Interface object = (parameters) -> {
    statement1
    statement2
    ...
    statementN
};
```

Consider the following interface.
```
interface OnSingleClickListener {

    void handleSingleClick();
}
```

To create an instance of the `OnSingleClickListener` interface, you would write
the following statement.

```
OnSingleClickListener listener = () -> {
    System.out.println("The button was clicked!");
}
```

This example creates an object that implements the `OnSingleClickListener`
interface.

Since the `handleSingleClick()` method does not accept any parameters, you leave
the parenthesis empty.

Since the body of the lambda expression in this example has only one statement,
you can further simplify the code like this.

```
OnSingleClickListener listener = () -> System.out.println("The button was clicked!");
```

You don't have to enclose a statement in braces, if it is the only statement 
in the lambda body.