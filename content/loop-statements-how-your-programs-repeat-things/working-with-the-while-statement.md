When it comes to loops, Java gives you three choices. You can go with the
complex for loop, which has all the gizmos and options to make most programmers
happy, or you can choose the simpler while loop for your programs.

The for statement is clearer and lays out all its plans in one place.
Whereas, the while statement gives you more flexbility. The important thing to
remember is that you can convert a for loop into a while loop, and vice versa.

The while loop is the simplest loop in Java. It simply executes a loop continuously
as long as a condition is true. While loops are useful in many situations, so
you use them a lot.

Generally in a while loop we say "while this condition is true, keep repeating
this action."

Here is a simple example that shows a while loop in real life. You eat from your
lunch box while there is food in it. Easy enough.

The general form of the while statement is like this.
```
while (condition)
    body
```

The while statement begins by evaluating the conditional expression. If the
expression is `true`, the body is executed. Then, the conditional expression
is evaluated again, and the whole process repeats. If the expression is `false`,
the body is not executed, and the while loop ends.

Note that the body of the while statement can either be a simple statement or a
compound statement.

Loops with multiple statements are very common. So you will commonly come across
code where a block is used to group statements.

Here's a simple program that uses a while loop to print the even numbers
from 2 through 10 on the console.

```
public class EvenNumbers {

    public static void main(String ... arguments) {
        int number = 2;
        while (number <= 10) {
            System.out.println(number);
            number += 2;
        }
    }
}
```

If you run this program, the following output is displayed on your console.
```
2
4
6
8
10
```

The conditional expression you used in the while loop shown in the previous
example is `number <= 10` (number is less than or equal to 10).
That means the loop repeats as long as the value of number is less
than or equal to `10`.

The body of the loop consists of two statements. Therefore, we enclose them in
braces. The first statement prints the value of `number`. Then, the second
statement adds `2` to `number`.

Notice that we have enclosed the statements in braces. This forms a
block statement. Since a block statement is a compound statement it can be
used with the while statement. The main advantage of the block statement
is that it allows you to write more than one statement under a clause.

We recommend you to use block statements with while statements, even if your
block contains only a single statement. Because blocks make your program more
readable. Additionally, if you later decide to add a few statements to the
loop, the braces are already there. This avoids bugs such as forgetting 
to add braces.

Here's a flowchart for this program. It can help you visualize the basic decision
making process of a loop.