+++
title = "The Object Class"
weight = 2
+++

Inheritance is comparable to how you inherited traits such as your height,
eyes, hair, DNA, and allergies from your parents. They in turn inherited
some of their traits from their parents, that is, your grandparents. Inheritance
of such tratis basically keeps going backwards in time till the very first people
who populated Earth, say Adam and Eve, the root of your ancestorial hierarchy.

Similarly, every class hierarchy has a root class. All the class hierarchies in
Java have the same class as their root class: the `Object` class. When the extends
clause is absent, an implicit extends clause inheriting the `Object` class is
provided by Java.

In Java, the `Object` class is the root of class hierarchy. In other words,
the `Object` class is the superclass of all classes in Java.

The `Object` class is special because it is the only class in Java that does not
inherit any other class. 

The `Object` class defines the following methods, which means that they are
available in every object.

  * The `clone()` method creates a clone of the object is being invoked against.

  * The `equals()` method determines whether one object is equal to another object.
    It compares two objects and returns `true` if both are same, otherwise it
    returns `false`.

  * The `finalize()` method is invoked by the Java Virtual Machine (JVM) before
    the object is destroyed.

  * The `getClass()` returns an object which represents the class of an object
    at runtime. This method is part of the reflection API, which allows you to
    dynamically load classes, create instances, and invoke methods.

  * The `hashCode()` method returns the hash code of the object.

  * When you invoke the `notify()` method it resumes execution of a thread
    waiting for the object.

  * Invoking the `notifyAll()` resumes the execution of all the threads waiting
    on the object.

  * You have already seen the `toString()` method. It returns a string that
    describes the object.
    
  * In order to wait for an object to signal from another thread, you invoke
    the `wait()` method.

The methods `getClass()`, `notify()`, `notifyAll()`, and `wait()` are declared
as final. You cannot override them.