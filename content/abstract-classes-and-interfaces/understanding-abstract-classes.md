+++
title = "Understanding Abstract Classes"
weight = 1
+++

In a class hierarchy, the classes at the top are abstract in their definitions.
Because these classes can define behavior and attributes common to all the
classes below them. Classes with specific behavior and attributes are usually
at the bottom of the hierarchy.

When you design a class hirerarchy, your first step is to factor out the common
behavior and attributes common to all the classes. In some situations you may
find yourself with a very abstract behavior, which prevents you from providing
a general implementation. Classes with such behavior are known as abstract classes.

Consider the following class which represents a shape.
```
class Shape {
    
    private String color;
    
    public void setColor(String color) {
        this.color = color;
    }
    
    public String getColor() {
        return color;
    }
    
    public float getArea() {
        return 0f;
    }
    
    public float getPerimeter() {
        return 0f;
    }
}
```

Imagine the shape is a graphical component. Thus, every shape has area, perimeter,
and say a color. The color attribute has corresponding accessors. Given area
and perimeter depend on variables defined by the subclasses, we cannot implement
their accessors.

At this level in the class hierarchy, you cannot provide general methods that
can calculate both area and perimeter for all shapes. Because each shape has
different formulas for area and perimeter. Even if you manage to find a work
around for a few shapes, you cannot keep all the shapes happy. This is why you
create dummy methods that always return zero. In the sense, these methods are
examples of abstract behavior.

However, the `Shape` class should never be instantiated directly. Because
some of its methods are dummies incapable of calculating anything. It makes no
sense to instantiate a class that is incomplete.

In order to tell the compiler that this class is incomplete and should not
be allowed to instantiate, we need to mark it as abstract. You can add the
`abstract` modifier to the class declaration to mark it as an abstract class.

Further, you need to add the `abstract` modifier to all the dummy methods.
You do not have to provide a body to abstract methods. Instead terminate the
declaration with a semicolon. 

Here is the general form of an abstract method.

```
modifiers abstract returnType name(parameters);
```

Here, the valid modifiers are `public`, `protected`, `synchronized`, and `strictfp`.
You cannot declare an abstract method as `private`, `final`, `native`, or `static`.

You cannot mark private methods as abstract because the subclasses cannot
implement private methods because they would be inaccessible to begin with.

You cannot mark abstract methods as final because final methods cannot be
overridden.

Abstraction is a concept associated with instance members of a class.
When an instance member is invoked, Java uses a mechanism known as dynamic
method dispatch, which means Java determines which instance method you are invoking
at runtime. Java determines which static method you are invoking at compile time.
Which means, invocation of static methods works differently. Therefore, you
cannot mark a `static` method as abstract.

An abstract method constitues of the method signature and the return type,
with no implementation. It serves as a placeholder so the subclasses can
implement it. You cannot declare an abstract method inside a class that is not
abstract.

Here is an abstract version of the `Shape` class.
```
abstract class Shape {
    
    private String color;
    
    public void setColor(String color) {
        this.color = color;
    }
    
    public String getColor() {
        return color;
    }
    
    public abstract float getArea();
    
    public abstract float getPerimeter();
}
```

In this example, the `getArea()` and `getPerimeter()` methods are abstract.
Which means, you will not be able instantiate the `Shape` class. If you try
to instantiate it with the `new` operator, the compiler generates errors.

Abstract classes can contain anything a normal class can contain, including
constructors, initializer blocks, and methods. Subclasses which extend abstract
classes inherit superclass members as usual.

You don't have to declare all the methods in an abstract class as abstract.
A class can provide implementation for some of its methods. In fact,
you can declare a class as abstract even when it has no abstract methods.
In which case, the class cannot be instantiated unless it is extended.

Here is an example of a `Rectangle` class which extends the `Shape` class.
```
class Rectangle extends Shape {

    private float length;
    
    private float breadth;

    public void setLength(float length) {
        this.length = length;
    }
    
    public float getLength() {
        return length;
    }
    
    public void setBreadth(float breadth) {
        this.breadth = breadth;
    }
    
    public float getBreadth() {
        return breadth;
    }

    @Override
    public float getArea() {
        return length * breadth;
    }
    
    @Override
    public float getPerimeter() {
        return 2 * (length + breadth);
    }
}
```

When you inherit an abstract class, you need to implement the abstract methods.
If your subclass is also incapable of implementing general behavior for its
subclasses, you can declare it as abstract. In which case, you do not have to
implement the abstract methods you inherited. Further, you can add other abstract
methods.

In fact, an abstract class can appear at any level in a class hierarchy. When
you want to instantiate it, you need to extend it and implement the abstract
methods.