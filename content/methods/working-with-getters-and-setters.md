+++
title = "Working with Getters and Setters"
weight = 5
+++

Object-oriented programming helps you hide the details of a class. You can
expose certain parts of your class to others.

You should generally avoid creating public fields. You can make all your
fields private. You can give access to the values in these fields with
*accessors*.

Accessors are methods which access fields on the behalf of the world outside
your class.

There are two types of accessors.
    * Get Accessor
    * Set Accessor

A get accessor is also known as **getter**. It is a method which gets the value
of a field.

A set accessor is also known as **setter**. It is a method that sets the value
of a field.

Accessors are usually named `getField` and `setField`. For example, for a
field named `age`, the accessors are named `getAge` and `setAge`.

Here is an example.

```
class Rocket {

    private double mass;
    private double velocity;
    private double acceleration;

    public void setMass(double m) {
        mass = m;
    }

    public double getMass() {
        return mass;
    }

    public void setVelocity(double v) {
        velocity = v;
    }

    public double getVelocity() {
        return velocity;
    }

    public void setAcceleration(double a) {
        acceleration = a;
    }

    public double getAcceleration() {
        return acceleration;
    }
}
```

In the above example, `mass`, `velocity, and `acceleration` are private fields.
You cannot access them directly outside the class. You need to use their accessors
instead.

Accessors have the following advantages over public fields.

 * You can create read-only properties. You can provide only the getter but not
   a setter. Which means other classes can only read the property, but cannot
   write.
 * You can avoid storing the value in a field. A getter can calculate the value.
   
Here is an example of a rectangle, where an accessor evaluates the value.

```
class Rectangle {

    private double width;
    private double height;

    public void setWidth(double w) {
        width = w;
    }

    public double getWidth() {
        return width;
    }

    public void setHeight(double h) {
        height = h;
    }

    public double getHeight() {
        return height;
    }

    public double getArea() {
        return width * height;
    }
}
```

* A setter can check if an invalid value is passed. It can *throw an exception*
 or provide a default value. You will learn more about exceptions later in
 this book.

 For example, imagine you have a class `Adult`. It has an integer property
 named `age`. Its value can be 18 or greater. You can write a setter which
 ignores invalid values like this.

```
class Adult {

    ...

    private int age;

    public void setAge(int a) {
        if (a >= 18) {
            age = a;
        }
    }

    public int getAge() {
        return age;
    }

    ...
}
```

In fact, using accessors is actually a design pattern known as the Accessor Pattern.
It is designed to provide a consistent way to read and write values of class
fields while hiding the fields from the outside world. This pattern is very
common because fields are usually private.