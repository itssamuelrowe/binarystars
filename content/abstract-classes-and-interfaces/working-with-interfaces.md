+++
title = "Working with Interfaces"
weight = 2
+++

As you design your class hierarchies, you soon learn that the simplicity of
single inheritance is restrictive. This is especially true when multiple unrelated
classes have common behavior and you want to factorize them. Other Object-Oriented
Programming (OOP) languages provide multiple inheritance, which solves this problem.
But multiple inherentance comes with its own problems. This leads to complicated
class designs, ambiguity and confusion.

This is why the creators of Java did not include multiple inheritance. Instead
Java offers a more friendly solution: interfaces.

An interface provides a template of behavior that classes should implement.
In other words, an interface specifies what a class should do, but does not 
implement it. They provide a significant advantage designing your program.

Unlike an abstract class, where you can provide instance methods and variables,
an interface does not allow instance variables and method implementations.

The syntax of an interface is very similar to a class. It does not allow
any instance variable and contains only abstract methods. Any number of classes
can implement an interface. 

A class can implement any number of interfaces. When your class implements an
interface, all the methods declared in the interface must be implemented. You
are free to implement the details in anyway you want. This is similar to multiple
inheritance, but without the baggage multiple inherintance brings with it.

Given interfaces form a separate hierarchy from your class hierarchy, sometimes
classes that are unrelated implement the same interface. Where you would normally
use multiple inheritance provided by languages such as C++, in Java you resort
to interfaces.

Interfaces enhance your design by taking advantage of the dynamic method dispatch
at runtime. This allows you to decouple your code from the actual implementation
and make your code generic and easy to refactor. This is a very powerful feature
interface offers. In fact, when you learn advanced Java frameworks such as Spring
and Java Persistence API (JPA), you will realize how powerful interfaces simply
are.

The general form of an interface is shown here.

```
interface name {

    constants
    methods
}
```

The `name` indicates the name of the interface. It can be any valid identifier.
We recommend you to follow the same naming conventions that you learnt for classes.
An exception to this is that interface names are usually adjectives because they
describe additional capability or quality that classes implement.

Unlike abstract classes, the methods that you declare in interfaces do not
require the abstract modifier. Their declaration does not have bodies.
They are terminated with a semicolons after the parameter list.

You cannot declare variables in an inteface. You can declare only static constants.
You do not have to add both the `static` and `final` modifiers, both are implicit.
Further, you need to initialize the constant with a value.

All the methods and constants are implicitly public.

Here is an example of an interface which represents a shopping list.

```
interface ShoppingList {
    
    void addItem(String item);
    void removeItem(String item);
}
```

In this example, we declared two methods. Each method represents basic actions
that can be performed on a shopping list.