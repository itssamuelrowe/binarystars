## Instance Members

Instance variables are variables that you declare inside a class body and
without the `static` keyword. They are declared outside methods, constructors,
and blocks. These variables are initialized when you create an instance of the class.
Further, each instance of the class gets a copy of these variables.

In fact, when any member of a class, except constructors, is declared
without the `static` keyword you are essentially declaring an instance member.
An instance member can be accessed only with a reference to an instance.

When you create an instance of a class, the instance gets its own copy of the
instance variables in memory. But Java treats other instance members specially.

In fact, each instance of class does not contain its own copy of instance members
such as methods, classes, interfaces and enumerations. Because multiple copies of
such members will exhaust the memory. Instead Java keeps only one copy of
such instance members and simulates as if each instance gets its own copy.
Actually, if memory were not a concern, each instance would get its own copy
of such members to improve performance.

## Static Members

Class variables are variables that you declare within a class with the `static`
keyword. They are outside methods, constructors, and blocks. Remember, you
declare class variables with the `static` keyword. Unlike instance variables,
each instance of a class does not get a copy of class variables.

In fact, when you declare any member of a class
with the `static` keyword, you are declaring a class member or a static member.
A class member can be accessed without a reference to an instance.

Static members belong to the class instead of a specific instance. Which means
if you make a member static, you can access it without an instance.
You should always remember that whenever you create an instance of a class,
the instance does not get its own copy of the static members.

You have already used the `static` modifier from the beginning of this course.
The main method is declared as static because the Java Virtual Machine (JVM)
does not create an instance of your main class before invoking the main method.
This is why you should always declare the main method as static.

Here is an example of a class variable.

```
public class Circle {
    
    public static double PI = 3.14159265F;
}
```

You can access a class member without a reference to an instance. You
can access a class member using the class name followed by the dot operator
(`.`) and the name of the member.

Here is an example of accessing the class variable `PI` from the previous
example.

```
area = Circle.PI * radius * radius;
```

In this example, we are calculating the area of a circle.

Further, you can also use an instance of a class to access its class members.
We recommend you to use the class name. This makes your code more clear.
But you can never access an instance member using a class name.