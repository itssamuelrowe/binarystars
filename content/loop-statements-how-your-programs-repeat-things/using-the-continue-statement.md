+++
title = "Using the Continue Statement"
weight = 4
+++

Sometimes it is useful to force an early iteration of a loop. In other words,
you might want to continue running the loop but stop processing the remainder
of the code in its body for this particular iteration.

In while and do-while statements, a continue statement causes control to be
transferred directly to the conditional expression that controls the loop.
In a for statement, control first goes to the updation section of the for statement
and then to the conditional expression. For all three loops, any intermediate code
is skipped.

The general form of a continue statement is like this.

```
continue label;
```

Here, the label is optional. You will learn more about labels in just a moment.

Continue is a simple statement therefore it ends with a semicolon.

Here is an example program that uses continue to cause two numbers to be printed
on each line:

```
class ContinueDemo {
    
    public static void main(String ... arguments) {
        for (int i = 0; i < 10; i++) {
            System.out.print(i + " ");

            if (i % 2 == 0) {
                continue;
            }
            
            System.out.println();
        }
    }
}
```

This code uses the modulus operator to check if `i` is even. If it is, the loop
continues without printing a newline.

Here is the output from this program.
```
0 1
2 3
4 5
6 7
8 9
```

In the case of nested loops, the loop nearest to the continue statement is affected.
You can override such behaviour using labels.

As with the break statement, continue statements may specify a label to describe
which loop to continue. This is especially useful in nested loop. Without a label,
continue affects the loop nearest to the continue statement. Using continue with
a label enables you to effect a particular loop.

Here is an example program that uses continue statement to print a triangular
multiplication table for 0 through 9.

```
class TriangularMultiplicationTable {

    public static void main(String ... arguments) {
        outer:
        for (int i = 0; i < 10; i++) {
            for(int j = 0; j < 10; j++) {
                if (j > i) {
                    System.out.println();
                    continue outer;
                }
                
                System.out.print(" " + (i * j));
            }
        }
        System.out.println();
    }
}
```

The continue statement in this example terminates the loop counting `j` and
continues with the next iteration of the loop counting `i`.

Here is the output of this program.

```
0
0 1
0 2 4
0 3 6 9
0 4 8 12 16
0 5 10 15 20 25
0 6 12 18 24 30 36
0 7 14 21 28 35 42 49
0 8 16 24 32 40 48 56 64
0 9 18 27 36 45 54 63 72 81
```

You will rarely come across continue statements. One reason is that Java provides
a various loop statements which fit most applications. However, for those
special circumstances in which early iteration is needed, the continue statement
provides a structured way to get your job done.