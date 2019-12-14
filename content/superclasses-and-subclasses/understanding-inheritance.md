+++
title = "Understanding Inheritance"
weight = 1
+++

Inheritance is a concept of object-oriented programming. You can derive a class
from another class with inheritance.

A class that you inherit is known as *parent class*, or *base class*, or
*superclass*.

A class which inherits is known as *child class*, or *derived class*, or
*subclass*.

Imagine you have a class that already has behavior and attributes that another
class needs. You do not have to rewrite or copy your code to have the same behavior
and attributes. With inheritance, your class automatically receives the behavior
and attributes from its superclass. Basically, a class becomes a combination of
its own features and all the features it inherits from the classes above it in
the hierarchy.

To inherit a class, you simply specify the class to inherit in the definition
of your class using the extends clause. The general form of the extends clause
is shown here.

```
class A extends B {
    ...
}
```

Here, `A` represents the name of your class. `B` represents the name of the
you want to inherit. In other words, `A` represents the name of the subclass
and `B` represents the name of the superclass.

A class can have only one superclass, but it can have an unlimited number of
subclasses. This type of inheritance is called single inheritance because each
class can have only one superclass.

In other object-oriented programming languages such as C++, classes can have
more than one superclass. This is called multiple inheritance. Java makes inheritance
simpler by allowing only single inheritance.

With inheritance, you can implement *is-a-type-of* relationships. Here are some
examples.
    * Cricket is a type of game.
    * A tiger is a type of animal.
    * A duck is a type of bird.
    * A mango is a type of fruit.

Here is an example that demonstrates the hierarchy of shapes.

```
class Shape {

    private float area;
    private float perimeter;

    public float getArea() {
        return area;
    }

    public void setArea(float area) {
        this.area = area;
    }

    public void setPerimeter(float perimeter) {
        this.perimeter = perimeter;
    }

    public float getPermeter() {
        return perimeter;
    }
}

class Square extends Shape {

    private float side;

    public float getSide() {
        return side;
    }

    public void setSide(float side) {
        this.side = side;
    }
}


class Rectangle extends Shape {

    private float length;

    private float breadth;

    public float getLength() {
        return length;
    }

    public void setBreadth(float breadth) {
        this.breadth = breadth;
    }

    public float getBreadth() {
        return breadth;
    }

    public void setBreadth(float breadth) {
        this.breadth = breadth;
    }
}

class Circle extends Shape {

    private float radius;

    public float getRadius() {
        return radius;
    }

    public void setRadius(float radius) {
        this.radius = radius;
    }
}

public class ShapeDemo {

    public static void main(String... arguments) {
        Square square = new Square();
        square.setArea(100);
        square.setPerimeter(40);
        square.setSide(10);

        Rectangle rectangle = new Rectangle();
        rectangle.setArea(70);
        rectangle.setPerimeter(34);
        rectangle.setLength(7);
        rectangle.setBreadth(10);

        Circle circle = new Circle();
        circle.setArea(314.28f);
        circle.setPerimeter(62.85f);
        circle.setRadius(10);
    }
}
```

In this example, we demonstrate an hierarchy of shapes. Consider three shapes:
squares, rectangles, and circles. Each 

To represent shapes, you can create a class named `Shape`. It describes features
common to all shapes, such as area and perimeter. Being the good citizens of
the Java world, you make these fields private. You create accessors to expose
them consistently.

We know that a square is a type of shape. Obviously, it has properties such
as area and perimeter. Instead of rewriting the accessors and fields to implement
these properties, you simply inherit the `Shape` class. Of book, `Square` has
`side`, which describes the length of its sides. Thus, we extend the features of
`Shape` by adding the field and accessors for `side`.

Similarly, a rectangle is a type of shape. It extends the `Shape` class to inherit
the `area` and `perimeter` attributes and their corresponding accessors.
A rectangle has four sides, with equal opposite sides known as length and breadth.
Therefore, we extend the features of `Shape` by adding these two fields and their
corresponding accessors.

In the `main()` method, we create an instance of `Square`, `Rectangle`, and
`Circle`. Although, we did not create accessors for area and perimeter
in these classes, we are still able to invoke their accessors because these
methods were inherited by them.

The `Square`, `Rectangle`, and `Circle` classes have is-a-type-of relationship
with the `Shape` class. Because they are all a type of shape.

You know that private fields are accessible only within the class they are declared.
Which means, when you inherit a class with private fields, you will not be
able to access them. In other words, private fields are not inherited by classes.
When you create an instance of the subclass, the instance is a combination of
the subclass and all the superclasses. Which goes to say the instance gets its
own copy of all the fields, including private fields declared throughout the
hierarchy. But they are only accessible by the classes in which they were
declared.

In order to access a field declared in a superclass from a subclass, the field
must be either declared as public or protected. If you declare the field as public,
any class can access it. If you want to limit the visibility of the field
only to your class hierarchy, declare it as protected. You must remember that
protected fields are accessible by other classes in the same package even if
they are not a part of your hierarchy.

You can inherit a class that inherits another class. Thus, inheritance forms
an hierarchy. Here is an example.

```
class Vehicle {
    String license;
    String make;
    String model;
    
    ...
}

class Car extends Vehicle {
    int seats;
    int wheels;
    int passengers;
    
    ...
}

class Sedan extends Car {

    ...
}

class Hatchback extends Car {

    ...
}
```

You can prevent a class from being inherited. You simply need to add the `final`
modifier in the declaration of the class.

Here is an example of a final class.
```
public final class Message {
    ...
} 
```