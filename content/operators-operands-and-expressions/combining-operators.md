The concepts explained in this course are very important. Don't worry if you
find the concepts confusing. You can always come back and view the video later.

You can combine operators to form complex expessions.

The order in which the operations are evaluated is determined by
the precedence of the operators involved in the expression.
For example, multiplication and division have a higher precedence than addition and subtraction.

Always remember, precedence rules can be overridden by explicit parentheses.

Parentheses raise the precedence of the operations that are inside them. This is
often necessary to obtain the result you desire.

When two operators share an operand the operator with the higher precedence goes
first. For example, `1 + 2 * 3`(1 plus 2 into 3) is treated as `1 + (2 * 3)`(2 into 3 the whole plus one), whereas `1 * 2 + 3` is treated as `(1 * 2) + 3` since multiplication has a higher precedence than addition.

But what happens when two operators with the same precedence
occur in the same expression? In such cases, the expression is evaluated
according to the associtivity of the operators involved.

For example, the expression x = y = z = 7 is equivalent to x = (y = (z = 7)) (z=7 y=z x=y)because the assignment operator has right-to-left associativity which means the operators are evaluated from left to right.

Here's another example. The expression 10 / 20 / 30 is equivalent to (10 / 20) / 30 (10 divided by 20 the whole divided by 30) because the / division operator has left-to-right associativity.

Further, some operators are associative. For example, the expression (x <= y <= z) is invalid.

The following table shows all operators in Java from highest to lowest precedence, along with their
associativity. You don't have to memorize them all. You will learn eventually with practise.

We recommend you to use parentheses whenever possible for clarity.