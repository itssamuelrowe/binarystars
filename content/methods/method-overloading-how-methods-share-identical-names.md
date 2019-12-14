+++
title = "Method Overloading: How Methods Share Identitical Names"
weight = 4
+++

Unlike variables, multiple methods in the same scope can have the same
name. This technique is known as method overloading. It is a feature of
polymorphism. Method overloading is a very useful feature.

Java differentiates methods using method signatures. A method signature is a part
of method declaration. It is the combination of the method name and the parameter
list. The return type of the method is not included in the signature.
Further, the names of the parameters are also not included.

In order to overload a method, the method signatures should be different. Which
means even if your method names are the same, you need to have different parameter
lists. When the methods have the same name but different parameter lists,
the methods are said to be overloaded.

When you invoke an overloaded method, Java uses the following conditions to
determine which version of the overloaded method you are calling.
    * The type of each argument you are passing.
    * The number of arguments you are passing.

This is the reason why overloaded methods must have different parameter lists.
Otherwise, Java won't be able to determine which version of the overloaded
method to call.

You have already used method overloading many times, without realizing it.
The `PrintWriter` class, which you access through `System.out` defines many
versions of the `println` method. It prints different types of data.

Here is the list of all the `println` methods.

```
void println()
void println(boolean value)
void println(char value)
void println(int value)
void println(long value)
void println(float value)
void println(double value)
void println(String value)
void println(char[] value)
void println(Object value)
```

Here is a simple example that computes area of squares and rectangles using
method overloading.

```
public class AreaComputer {

    /**
     * Compute the area of a square.
     */
    public static int computeArea(int side) {
        return side * side;
    }
    
    /**
     * Compute the area of a rectangle.
     */
    public static int computeArea(int length, int breadth) {
        return length * breadth;
    }
    
    public static void main(String... arguments) {
        int s = 10;
        int areaOfSquare = computeArea(s);
        System.out.println("The area of square with side " +
            s + " is " + areaOfSquare);
        
        
        int l = 10;
        int b = 5;
        int areaOfRectangle = computeArea(l, b);
        System.out.println("The area of rectangle with " +
            l + " and " + b + " as length and breadth, respectively, is " +
            areaOfRectangle);
    }
}
```

The output of this program is shown here.

```
The area of square with side 10 is 100
The area of rectangle with 10 and 5 as length and breadth, respectively, is 50
```

As you can see, computeArea() is overloaded two times. The first version accepts
a single integer named `side`. The second version accepts two integer parameters
named `length` and `breadth`, respectively.

When you invoke a method, Java looks for a match between the arguments passed
and the method parameters declared.

When `computeArea` is called the first time with a single integer argument,
the method which computes the area of a square is invoked.

Similarly, when `computeArea` is called the second time with two integer
arguments, the method which computes the area of a rectangle is invoked.

The results are respectively stored in variables before printing.

Overloading is useful because it allows you to declare and invoke related methods
with the same name.

For example, you could implement an operation such as `computeVelocity`, which
obviously evalutes the velocity of something, say a bike. The name `computeVelocity``
represents the general action that is being performed. You could implement
two different versions of calculations using different formulas. Assume
one version accepts distance and time, whereas another version accepts force,
mass and time. With method overloading you could easily implement this. Otherwise,
you would have to come up with different names for each method!

When you overload a method, each version can implement anything. You don't
have to relate the methods to one another. 

We recommend you to always overload methods that perform the same operation but
in different ways.