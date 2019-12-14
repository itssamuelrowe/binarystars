All loops end when a test condition fails. There might be situations where
something occurs during the execution of a loop, and you want to exit the loop
early. In such cases, you can use the break statement.

In fact you have already seen a simple use of the break statement in the switch
statement. In this section, you will learn more about the break statement.

The general form of a break statement is like this.

```
break label;
```

Here, the label is optional. You will learn more about labels in just a moment.

Break is a simple statement therefore it ends with a semicolon.

Basically, the break statement stops the execution of a switch statement.
The `break` keyword, when used inside a loop, does the same thing, that is, it
immediately halts execution of the loop.

In the case of nested loops, the loop nearest to the break statement is terminated.
You can override such behaviour using labels.

A break statement accepts an optional label that indicates which loop to terminate.
This is especially useful in nested loop. Without a label, break jumps outside
loop nearest to the break statement. Using break with a label enables you to
terminate a particular loop.

The general form of a label is shown here.

```
label : // loop statement
```

To use a labeled loop, add the label before the initial part of the loop with a
colon between the label and the loop. Then, when you can use the break statement
add the name of the label after the `break` keyword.

Labels can be used with any type of loop available in Java.