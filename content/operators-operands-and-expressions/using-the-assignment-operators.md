The assignment operator helps you assign a value to a variable. You have
already seen many examples of this operator. **It assigns the value on its
right to the operand on its left.**

For example, here's an example of the assignment operator in use.
```
int vehicles;
int cars = 100;
vehicles = cars;
```

In the above example, we created a variable named `vehicles`. Think that
it stores the number of vehicles you own. We also created another variable
named `cars`. Think that it stores the number of cars you own.

When we say `vehicles = cars`, we are storing the value stored in `cars`
to `vehicles`. Because the assignment operator assigns the value on its
right to the operand on its left.

Always remember, your expression on the left hand side should be capable of storing a value.

For example, the following statement does not compile.

```
a + b = c * d
```

Because the expression on the left hand side evaluates to a value.
A value simply cannot store another value.

Before we continue with the other concepts of the assignment operator, you need to understand that an assignment in Java is simply an expression and not a statement.

For example, `a = 7` is an expression. It becomes an expression statement only when you add a semicolon to the end like this.

```
a = 7;
```

Remember that I told you that an operator always returns a result? If that's true, what does the assignment operator return?

It returns the value that it assigned to a variable.

For example, the result of `s = 7` evaluates to `7`.

Similarly, the expression `r = (a * a) - (b * b)` returns the result of the expression `(a * a) - (b * b)`.

So, what is the use of the assignment operator returning a result?
Well, this allows us to use multiple assignments in the same expression.

Here's an example.
```
a = 10;
b = a;
c = b;
```

You could write this like this:
```
a = b = c = 10;
```

Given, the associativity of the assignment operator is right-to-left, first `c = 10` is evaluated. It returns `10` which is assigned to `b`. Again, `b = c` returns `10` which is assigned to `a`. Thus, all the variables are assigned to `10`.

Now, consider another complicated case.

```
b = 7;
a = (b = 9) + 10;
```

As in any expression, the expression inside the parenthesis is evaluated first. Here, `b` is assigned to `9`. Since an assignment returns whatever was assigned, in this case `9` is returned. The `9` is then added to `10`. Then the result, that is 19, is stored in `a`.