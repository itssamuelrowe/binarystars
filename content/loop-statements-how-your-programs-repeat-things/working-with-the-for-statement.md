+++
title = "Working with the For Statement"
weight = 6
+++

In JDK 5, a new form of the for statement was released. The first is the
traditional form that has been in use since the original version of Java.
The second is the new form which is called as the enhanced for loop or the for-each loop.
You will learn about the traditional for statement in this section. You will learn about
the enhanced for loop later in book.

The general form of the traditional for statement is shown here.
```
for (initialization; condition; updation)
    statement
```

Note that the body of the for statement can either be a simple statement or a
compound statement.

Loops with multiple statements are very common. So you will commonly come across
code where a block is used to group statements.

When the loop first starts, the initialization part of the loop is executed. 
Generally, this is an expression that sets the value of the loop control variable.

The loop control variable is a variable that acts as a counter for controlling
the loop. It is important to understand that the initialization expression is
only executed once.

Next, the conditional expression is evaluated. This must be a boolean expression.
It usually tests the loop control variable against a target value.
If this expression is `true`, then the body of the for statement is executed.
If it is `false`, the loop terminates.

Next, the updation portion of the loop is executed. This is usually an expression
that increments or decrements the loop control variable.

The loop then evaluates the conditional expression again and the whole process
repeats.

This process repeats until the conditional expression evaluates to `false`.

Here is an example which counts from 1 to 10.

```
class CountWithForLoop {

    public static void main(String ... arguments) {
        int i;
        for (i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

This program produces the following output.

```
1
2
3
4
5
6
7
8
9
10
```

Notice that we have enclosed the statements in braces. This forms a
block statement. Since a block statement is a compound statement it can be
used with the for statement. The main advantage of the block statement
is that it allows you to write more than one statement under a clause.

We recommend you to use block statements with for statements, even if your
block contains only a single statement. Because blocks make your program more
readable. Additionally, if you later decide to add a few statements to the
loop, the braces are already there. This avoids bugs such as forgetting 
to add braces.

## Declaring Loop Control Variables During Initialization

Often the variable that controls a for loop is only needed inside the loop
and is not used anywhere else. In such situations, it is possible to declare
the variable in the initialization part of the for statement.

For example, here is the previous example with the loop control variable `i`
declared in the initialization part of the loop.

```
class CountWithForLoop {

    public static void main(String ... arguments) {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

When you declare a variable like this, you can use the variable only in the for
statement. In other words, you cannot read or write a value to it outside the
loop. It just won't exist outside the loop.

If you need to use the loop control variable outside the loop, you should not
declare the variable in the initialization part. Declare it outside the for
statement.

Here is a simple program that determines whether a number is prime or not.
Notice that the loop control variable `i` is declared inside the for statement
because it is not used outside the loop.

```
public class PrimeNumber {
    public static void main(String ... arguments) {
        int number = 7;
        boolean prime = true;
        for (int i = 2; i <= num / i; i++) {
            if ((num % i) == 0) {
                prime = false;
                break;
            }
        }
        
        if (prime) {
            System.out.println(number + "is prime.);
        }
        else {
            System.out.println(number + "is not prime.");
        }
    }
}
```

You will learn more about break statement later in this book. For now, just
remember it terminates a loop immediately.

## Evaluating Multiple Expressions During Initialization and Updation

In some situations, you will want to evaluate more than one expression during
initialization. Similarly, you may want to evaluate more than one expression
during updation.

For example, consider the loop in the following program.

```
public class MultipleExpressionsWithForLoop {
    
    public static void main(String ... arguments) {
        int a;
        int b;
        b = 19;
        for (a = 7; a < b; a++) {
            System.out.println("a = " + a);
            System.out.println("b = " + b);
            b--;
        }
    }
}
```

As you can see, the loop is controlled by two variables. But the program includes
only `a` in the initialization part. You can make the program expressive if you
initialized `a` and `b` together.

To write two or more expressions in the initialization part, seperate the expressions
by a comma.

Using the comma, the previous example can be written as follows.

```
public class MultipleExpressionsWithForLoop2 {
    
    public static void main(String ... arguments) {
        int a;
        int b;
        for (a = 7, b = 19; a < b; a++) {
            System.out.println("a = " + a);
            System.out.println("b = " + b);
            b--;
        }
    }
}
```

In fact, you can include two expressions in the updation part as well.
You just need to seperate the expressions by a comma.

Using the comma, the previous example can be written as follows.

```
public class MultipleExpressionsWithForLoop2 {
    
    public static void main(String ... arguments) {
        int a;
        int b;
        for (a = 7, b = 19; a < b; a++, b--) {
            System.out.print("a = " + a);
            System.out.println(", b = " + b);
        }
    }
}
```

In this example, the initialization portion sets the values of both `a` and `b`.
Similarly, the two comma separated expressions in the iteration portion are
executed in the order they are written each time the loop repeats.

The program generates the following output.

```
a = 7, b = 19
a = 8, b = 18
a = 9, b = 17
a = 10, b = 16
a = 11, b = 15
a = 12, b = 14
```

The for statement is very flexible. In fact, the initialization, the conditional
expression and the updation parts of the for statement are all optional.

Here's an example that prints 1 to 10 without the initialization and the updation
parts.

```
public class CountWithForLoop2 {
    
    public static void main(String ... arguments) {
        int i = 1;
        for (; i <= 10;) {
            System.out.println(i);
            i++;
        }
    }
}
```

The example produces the following output.

```
1
2
3
4
5
6
7
8
9
10
```

If you carefully notice, the semicolons are written even when the initialization
and the conditional parts are absent.

We recommend that you simply use the while loop when your program design requires
you to skip parts of a for statement.

Further, you need to remember that when the conditional expression is absent
the for loop becomes an infinite loop. In other words, it is assumed that
the conditional expression always evaluates to `true`.

An infinite loop is simply a loop that has no termination condition. In other
words, the conditional expression of the loop always evalutes to `true`.

You can create an inifite loop with a for statement like this.
```
for (;;)
    statement
```

You can rewrite the previous example like this.

```
for (; true;)
    statement
```

In fact, you can create an infinite loop with any loop statement available
in Java.

Here's the general form of an infinite loop using the while statement.

```
while (true)
    statement
```

There are many programs which require infinite loops. For example, Graphical
User Interface (GUI) applications usually have infinite loops waiting for user
interaction.

However, infinite loops are really just loops with special termination requirements.
Later in this chapter, you will learn about the break statement which allows
you to terminate any loop, even infinite loops.