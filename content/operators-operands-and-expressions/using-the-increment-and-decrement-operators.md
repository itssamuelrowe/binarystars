+++
title = "Using the Increment and Decrement Operators"
weight = 7
+++

In this section you will learn about the increment and decrement operators.

One of the most common operations in programming is adding or subtracting 1
from a variable.

Adding 1 to a variable is called *incrementing* the varible. The traditional way to increment a variable is written as:

`a = a + 1`

Here, the expression `a + 1` is first evaluated, then the result is assigned to the varible `a`.

Similary, subtracting 1 from a variable is caled *decrementing* the variable. Again, the traditional way to decrement a variable is
written as:

`b = b - 1`

Here, the expression `b - 1` is first evaluted, then the result is assiged to the variable `b`.

Java provides an easier way to do such calculations via the increment operator (written as ++) and the decrement operator (written as --).

Thus, the above expression `a = a + 1` becomes `a++`.
Similarly, the expression `b = b - 1` becomes `b--`.

You must always remember that you can use the increment and decrement
operators only on variables. You cannot use it with literals or other expressions. For example, the following expressions will
generate errors.

b = 7++;
a = (a + b)--;

The increment and decrement operators are special unary operators.
They can be placed either before or after a variable. The placement of the operator may have a significant effect on 
how the expression is evaluated.

When the operator is prefixed to a variable, the value in the variable is first used for computing the result and then incremented.

When the operator is suffixed to a variable, the value in the variable is first incremented and then the result is computed.

Based on the placement of the operator the increment operator is divided into two types.
 * Postfix Increment Operator
 * Prefix Increment Operator

Similarly, the decrement operator is divided into two types.
 * Postfix Decrement Operator
 * Prefix Decrement Operator
 
Don't worry if you find these concepts confusing. Most people find these concepts confusing. You will eventually learn them with practice.

Let's consider the following statements with an expression that uses a postfix increment operator.

```
int a = 6;
int b = 5;
int c = a * b++;
```

Can you guess the value of `c`?

It is assigned to `30`. Because when its assignment is evaluated, the original value of `b` (that is, 5) is used in the multiplication. Then `b` is incremented to `6`.

Now, consider this example, with a prefix increment operator.

```
int a = 7;
int b = 5;
int c = a * ++b;
```

Can you guess the value of `c` now?

This time `c` is `42`.

Because when its assignment is evaluated, the value of `b` is first incremented to `6` before the multiplication is performed. Thus, `c` is assigned to `42 `.

As the increment and decrement operators are usually confusing for beginners when
used with other operators in expressions, I suggest that you use them
separately until you are used to them.

For example, assume the following code.

```
c = a * ++b;
```

You can instead write this as shown here.

```
b++;
c = a * b;
```

This makes your code simpler and more readable.