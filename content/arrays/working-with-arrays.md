+++
title = "Working with Arrays"
weight = 2
+++

In order to work with arrays you need follow these steps.

 * Declare a variable to reference the array object.
 * Create a new array object.
 * Assign the reference of the array object to the array variable.
 * Store information in the newly created array.

## Declaring Array Variables

Before you start working with an array, you need to create a variable that
can store a reference to the array object.

Here is the general form of an array variable declaration statement.
```
type[] identifier;
```

Here, the `type` indicates the type of elements stored in the array. You can
name the variable with any valid identifier.

The square brackets serve two purpose.

 * They help you differentiate your array variable from regular variable declarations.

 * The square brackets actually indictae the dimension of the array. When you
   write a single pair it indicates one dimensional array. Similarly, when you
   write two pairs they indicate two dimensional array, and so on. You will learn
   about array dimensions later in this chapter.

Optionally, you can write the square brackets after the identifier. The position
of the brackets does not matter unless you declare multiple variables in the same
statement. If you place the brackets after the type and before any identifier,
the brackets apply to all the variables. Similarly, if you place the brackets
after an identifier, the brackets apply only to that variable.

We recommend you to stay away from declaring multiple variables in the same
statement. This makes your code less readable.

Here is an example of array variable declarations.
```
String[] names;
Object objects[];
int[] marks;
Student students[];
```

## Creating Array Objects

After you declare the array variable, you need to create an array object and
assign its reference to the variable. Unlike other objects, arrays can be created
in two different ways. The first technique is to use an array initializer and
the other is to use the new operator.

An array has a fixed length that is set when your create it. You cannot change
the length of an array after you create it. You can determine the length of an
array by using the length field of an array object.

### Using Array Initializer

An array initializer is a list of expressions, separated by commas. The list
of expressions is enclosed within braces. The commas separate the values of the
array elements. The array will be large enough to hold the number of elements you
specify in the array initializer.

With this technique, you don't have to use the new operator. However, you can
use this syntax only with the array variable declaration statement.

The general syntax of an array initializer is shown here.
```
type[] identifier = {
    expression1,
    expression2,
    ...,
    expressionN
};
```

The main advantage of this technique is, when you know the initial values
of your array you don't have to write multiple statements for allocating and
initializing your array.

For example, to store the days of the week you would create an array like this.
```
public class DaysOfWeek {

    public static void main(String ... arguments) {
        String[] daysOfWeek = {
            "Sunday",
            "Monday",
            "Tuesday",
            "Wednesday",
            "Thursday",
            "Friday",
            "Saturday"
        };
        System.out.println("The second day of the week is " + daysOfWeek[1]);
    }
}
```

In this example, you create an array of String. It consists of the days in a
week. A print statement prints the second day of the week. Notice that we used
`1` as the index to access "Monday". This is because array indexes start from
zero.

## Using the New Operator to Allocate Array Objects

Arrays are objects in Java. Therefore, you can use the new operator to create a
new instance of an array. However, the syntax of the new operator is bit different
when you allocate an array.

Here is the general syntax of the new operator when allocating an array.
```
new type[size]
```

Here, the type indicates the component type of the array.

The `size` indicates the capacity of the array, that is, the number of elements
it can store.

Here is an example of allocating an array capable of storing 7 object references.
```
Object[] objects = new Object[7];
```
In this example, the declaration and allocation is combined in the same statement.
It allocates an array with 7 slots, where you can store seven references.

When you create an array object using the new operator, you are basically
creating empty slots where you can store references to objects. You should
remember that allocating an array does not allocate objects in the slots. You
must manually allocate objects and store their references in the array later.

In fact, when you create an array with a reference component type, Java
automatically initializes the slots to null reference. The keyword null refers
to a null object and can be used stored in any reference variable. Unlike C and
C++, the null reference is not equivalent to 0 or the null character (`\0`).

Here is another example of allocating an array that can store integers.
```
int marks[] = new int[10];
```
When you create an array with a primitive component type, Java automatically
initializes the slots to `0` for numeric types, `\0` (null character) for
the character type, and `false` for the boolean type.

An array size can be zero or more. If you specify a negative size, Java throws
the `NegativeArraySizeException`.

Here is an example of allocating a negative sized array.
```
public class NegativeArraySizeDemo {

    public static void main(String ... arguments) {
        String[] daysOfWeek = new String[-1];
    }
}
```

When you run this example, Java throws an exception like this.
```
Exception in thread "main" java.lang.NegativeArraySizeException: -1
        at NegativeArraySizeDemo.main(NegativeArraySizeDemo.java:4)
```

## Initializing Array Objects

Because each slot in an array contains a default value when you create it, you
must assign a value to each slot before using it.

Once you have allocated an array, you can access a specific element in the array
using the index enclosed in square brackets, known as the subscript operator.
An index starts at zero and extend to `n - 1`, where `n` is the size of the array.

Here is the general form of accessing an element in an array using the subscript
operator.
```
identifier[index]
```

The identifier represents the name of the array variable. The index indicates
the element slot which you want to access.

Here is an example which creates an array of three integers and assigns their
respective slots.

```
int[] marks = new int[3];
marks[0] = 40;
marks[1] = 63;
marks[2] = 55;
```

Here is another version of the days of the week program we saw earlier.
```
public class DaysOfWeek {

    public static void main(String ... arguments) {
        String[] daysOfWeek = new String[7];
        daysOfWeek[0] = "Sunday";
        daysOfWeek[1] = "Monday";
        daysOfWeek[2] = "Tuesday";
        daysOfWeek[3] = "Wednesday";
        daysOfWeek[4] = "Thursday";
        daysOfWeek[5] = "Friday";
        daysOfWeek[6] = "Saturday";
        System.out.println("The fourth day of the week is " + daysOfWeek[3]);
    }
}
```

In this example, you create an array of String. It consists of the days in a
week. The array is manually initialized by assigning each slot. A print statement
prints the fourth day of the week. Notice that we used `3` as the index to access
"Wednesday". This is because array indexes start from zero.

## Accessing Array Elements

After you have an array with initial values, you can read, modify, and test the
values in each slot. The value in a slot is accessed using the subscript operator.
You can write expressions like this using the subscript operator.
```
array[index] = value;
```

Whenever you try to access an element with an index, Java makes sure that you
are specifying a valid index. The index should always be greater than or equal
to zero and lesser than the size of the array, known as the arrays boundaries.
Unlike C and C++, in Java you cannot access a slot outside the array’s boundaries.
In case you try to access an element outside the arrays boundaries, Java
throws `ArrayIndexOutOfBoundsException`.

Here is an example which triggers an `ArrayIndexOutOfBoundsException`.
```
public class InvalidDayOfWeek {

    public static void main(String... arguments) {
        String[] daysOfWeek = new String[7];
        daysOfWeek[0] = "Sunday";
        daysOfWeek[1] = "Monday";
        daysOfWeek[2] = "Tuesday";
        daysOfWeek[3] = "Wednesday";
        daysOfWeek[4] = "Thursday";
        daysOfWeek[5] = "Friday";
        daysOfWeek[6] = "Saturday";
        System.out.println("The seventh day of the week is " + daysOfWeek[7]);
    }
}
```

This example produces the following output.

```
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: Index 7 out of bounds for length 7
        at InvalidDayOfWeek.main(InvalidDayOfWeek.java:12)
```

Since the size of the array is 7, the last valid index is 6. In this example,
the program tried to access the slot at index 7, which is invalid index. 
This is why Java throws an `ArrayIndexOutOfBoundsException`.

Every array object exposes a field called `length`. You can use this to determine
the size of an array. Note that this field is immutable, which means you cannot
modify it without making your compiler grumpy.

## Combining Array Allocation and Initializer

You cannot directly use the array initializer in an expression outside a variable
declaration statement. However, you can combine array allocation and initializer
in any expression.

Here is the general syntax which allows you to combine array allocation and
array initializer.

```
new type[] {
    expression1,
    expression2,
    ...
    expressionN
}
```

Here, you do not have to specify the number of elements in your array. Therefore,
you can leave the square brackets empty. The list of expressions enclosed by
the braces consist of the values which are assigned to the slots. You must
separate each expression with a comma.

Here is an example of this technique.
```
new int[] { 10, 20, 30, 40, 50 }
```