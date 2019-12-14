In this lecture, you will learn about the arithmetic operators in Java.

You can perform addition, subtraction, multiplication, and division with the
arithmetic operators. They are similar to operators in basic mathematics.

| Operator | Description                  |
|----------|------------------------------|
| +        | Addition                     |
| -        | Subtraction                  |
| *        | Multiplication               |
| /        | Division (returns quotient)  |
| %        | Division (returns remainder) |

## Addition

The addition operator, written as plus `+` accepts two operands. It adds both the operands 
that you specify and returns their sum as its result. You can add two
constants, a constant and a variable, or two variables.

Here's an example.
```
int age = 10;
int ageAfter10Years = age + 10;
```

## Subtraction

The subtraction operator, written as minus `-` accepts two operands. It subtracts the
second operand from the first operand. You can subtract a constant from
another constant, a constant from a variable, or a variable from another
variable.

Here's an example.
```
int age = 10;
int ageBefore10Years = age - 10;
```

## Multiplication

The multiplication operator, written as asterisk`*` accepts two operands. It multiplies both the operands 
that you specify and returns their product as its result. You can multiply two
constants, a constant and a variable, or two variables.

Here's an example.
```
float increment = 1.2;
float salary = 10000;
float newSalary = increment * salary;
```
In algebra, you can write a number next to a variable and
imply multiplication. For example in algebra, `8y` means eight times y. But this is not the case in Java. You always
need to write the asterisk to indicate multiplication.

## Division

The division operator, written as forward slash  `/` accepts two operands. It divides one operand
by another and returns the quotient as its result. You can divide two
constants, a constant and a variable, or two variables.

Here's an example.
```
float favorable = 1;
float total = 6;
float probability = favorable / total;
```

When you add two `int` values, the result is an `int` value, even if you assign the result to a `double` variable.

## Remainder

In Java, the modulus `%` operator does not calculate percentage. **It divides
one operand by another and returns the remainder as its result.** This operator is known as the modulus operator.
You can divide two constants, a constant and a variable, or two variables.

```
int a = 21;
int b = 2;
int c = a % b;
```

For example, when you divide 21 by 2 the quotient is 10 and the remainder is 1. Thus, in this example `c` is equal 
to 1.