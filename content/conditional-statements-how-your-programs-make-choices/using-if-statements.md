+++
title = "Using If Statements"
weight = 2
+++

The if statement is one of the most important statements in any
programming language. The following sections describe the various
forms of the if statement in Java.
Basically, the if statement allows your program to branch conditionally.
It is a compound statement.

Here is the general form of the *if statement*.

```
if (condition)
	statement
else
	statement
```

Here, a statement may be either a simple statement or a compound
statement. The condition is any expression that evaluates to a Boolean
value.

The if statement is divided into two clauses: if clause and else clause.
The if clause begins with the if keyword. It accepts a condition,
enclosed in parenthesis. Similarly, the else clause begins with the else
keyword. It is optional. In other words, if you don’t write the else clause
in your if statement, the compiler won’t complain.

If the condition specified to the if clause evaluates to true, then the
statement under the if clause is executed. Otherwise, the statement
under the else clause is executed.

Here is a simple example of the if statement.

```
public class CanIVote {

    public static void main(String... arguments) {
        int age = 18;
        if (age >= 18) {
            System.out.println("You are eligible to vote!");
        }
    }
}
```

In this example, a variable named age is initialized to 18. Using the if
statement your program checks if the user is 18 or above. If the
condition evaluates to true, the user is allowed to vote. Which we
indicate by printing the message `"You are eligible to vote!"`

The output of this program is shown below.

*You are eligible to vote!*

As you can see, the else clause was not written in this example. By now
if you compiled and ran this program, you wold know that the compiler
didn’t generate any errors. This is because the else clause is optional.

Can you guess what would have happened if the Boolean expression
evaluated to false in this example? The entire if statement would have
been skipped because the else clause is absent.

Notice that we have enclosed the print statement in braces. This forms a
block statement. Since a block statement is a compound statement it can
be used with the if statement. The main advantage of the block
statement is that it allows us to write more than one statement under a
clause.

We recommend you to use block statements with if statements, even if
your block contains only a single statement. Because blocks make your
program more readable. Additionally, if you later decide to add a few
statements to the clause, the braces are already there. This avoids bugs
such as forgetting to add braces.

Here's the same example, without using a block statement.
```
public class CanIVote {
    public static void main(String... arguments) {
        int age = 18;
        if (age >= 18)
            System.out.println("You are eligible to vote!");
        }
    }
}
```

We terminate the print statement with a semicolon because the print
statement is basically an expression statement. And if you remember, an
expression statement is a simple statement and all simple statements
must end with a semicolon.

Now, let's extend the program to print a message when the user is not
eligible to vote.

```
public class CanIVote2 {

    public static void main(String... arguments) {
        int age = 14;
        if (age >= 18) {
            System.out.println("You are eligible to vote!");
        }
        else {
            System.out.println("Sorry, kid. You cannot vote.");
        }
    }
}
```

The if clause is exactly the same as the previous example. The only
changes here are the else clause and the age variable initialized to 14.
Since the condition evaluates to false, the if clause is skipped and the
else clause is executed. The output of this program is shown below.

*Sorry, kid. You cannot vote.*

Notice that the statements inside the blocks are indented. Indentation
refers to the space and tab characters that you write before you write any
visible characters. This makes the structure of your code more obvious.
This is not required, because Java ignores white space. But it is always a
good practice to indent your code. Usually, text editors and IDEs take
care of indentation for you.

Generally, you should indent anything that is inside braces. Braces are
not only used in block statements, they are also used in many constructs
throughout Java, including methods, classes, interfaces, enumerations,
and so on. Although you have not learnt them yet, you should indent
these constructs, too. Don’t worry if you forget this guideline, we will
remind you to use indentation when you learn about them in the
upcoming chapters.

You can write a block statement inside another block statement. You
can think of the outer block statement as level 1 and the inner block 
statement as level 2. We recommend you to increment your indentation
by four space characters for each level.

Here is a modified version of the previous example which includes
comments that indicate the block level.

```
// level 1, 0 spaces
public class CanIVote3 {

    // level 2, 4 spaes
    public static void main(String... arguments) {
        int age = 14;
        // Level 3, 8 spaces
        if (age >= 18) {
            // Level 4, 12 spaces
            System.out.println("You are eligible to vote!");
        }
        else {
            System.out.println("Sorry, kid. You cannot vote.");
        }
    }
}
```

Remember, the indentation by itself does not create a block. You need
to enclose the statements with braces. Also, some programmers prefer
to write the opening brace of the block statement on the same line as the
if clause, like how we wrote in the voting example. However, you can
write the opening brace on a fresh line as shown below.

```
public class CanIVote4
{
    public static void main(String... arguments)
    {
        int age = 14;
        if (age >= 18)
        {
            System.out.println("You are eligible to vote!");
        }
        else
        {
            System.out.println("Sorry, kid. You cannot vote.");
        }
    }
}
```

Where you write the brace is simply a matter of style, so either position
is acceptable.