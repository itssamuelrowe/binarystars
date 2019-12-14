+++
title = "Overriding Methods"
weight = 3
+++

A subclass inherits all the behavior and attributes of its superclass. It can then
extend the behavior and attributes of its superclass. In fact, a subclass can
change the behavior provided by its superclass. This is known as *overriding*.
Overriding methods is a feature of polymorphism. In this section, you will learn
about overriding methods.

When you call an instance method, Java looks for the definition of the method
in the object’s class. If it does not find it, Java looks up for the method
in its superclasses, all the way to the `Object` class, until the method definition
is found. If the definition is not found, the method does not exist.

Inheritance allows you to define methods in superclasses and use them in
instances of your subclasses. This helps you avoid rewriting the code in your
subclasses. However, sometimes you may want to invoke a method but change its
behavior which was defined in a superclass. In such cases, you can alter it. This is
known as method overriding.

To override a method in a subclass you simply need to define the method
in your subclass with the same signature and return type. Java determines if
a method is overridden by comparing the signature of your method in the subclass
and the superclass. If the signatures match, then that method is considered as
overridden. When you invoke that method, the overridden version is executed instead
of the one in the superclass.

Consider the following example which prints the popular lines of the characters
from Friends.

```
class Friend {

    public String getPopularLine() {
        return "Unknown";
    }
}

class JoeyTribbiani extends Friend {

    @Override
    public String getPopularLine() {
        return "How you doin'?";
    }
}

class ChandlerBing extends Friend {

    @Override
    public String getPopularLine() {
        // PS: Could Chandler be more funny?
        // This is the only program I have ever written laughing.
        return "Until I was 25, I thought that the only response to 'I love you' was 'Oh crap!'";
    }
}

class PhoebeBuffay extends Friend {

    @Override
    public String getPopularLine() {
        // That's it. I'm off to watch Friends.
        return "They don't know that we know they know we know.";
    }
}

public class Friends {

    public static void main(String ... arguments) {
        Friend joey = new JoeyTribbiani();
        System.out.println("Joey: " + joey.getPopularLine());

        Friend chandler = new ChandlerBing();
        System.out.println("Chandler: " + chandler.getPopularLine());

        Friend phoebe = new PhoebeBuffay();
        System.out.println("Phoebe: " + phoebe.getPopularLine());
    }
}
```

When you compile this example, the compiler produces four files, one for each
class. The output of the program is shown here.

```
Joey: How you doin'?
Chandler: Until I was 25, I thought that the only response to 'I love you' was 'Oh crap!'
Phoebe: Until I was 25, I thought that the only response to 'I love you' was 'Oh crap!'
```

The `Friend` class defines a method called `getPopularLine()`. It always
returns the string `"Unknown"`.

To demonstrate method overriding, we created three other classes called
`JoeyTribbiani`, `ChandlerBing` and `PheobeBuffay` which inherit the `Friend`
class. Each of these classes define the `getPopularLine()` method with the same
signature and return type. Thus, they override the `getPopularLine()` method in
their respective classes.

Sometimes you may misspell a method name or change the signature by accident in
your subclass. Since Java does not force your subclass to override the definition
of a method, you may end up creating a new method instead of overriding a method
that exists in your superclass.

You always need to make sure that you have correctly overridden a method. Java
provides an annotation called `Override`. With this annotation you can tell the
compiler to check if you have correctly overridden a method.

An annotation is a special interface that provides supplemental information
about your source code. They are similar to comments, except they are not ignored
by the compiler. You will learn more about interfaces and annotations in the next
chapter. Annotations start with `@`. They provide information about your source 
code to tools such compilers. 

In the `main()` method we create an instance of each of the subclasses of `Friend`.
We assign the instances to variables of type `Friend`. This is valid because Java
implicitly casts the instance to `Friend`, because it is the superclass.

You can prevent a subclass from overriding a method. You simply need to add
the `final` keyword in the method declaration. When a subclass tries to override
a final method, the compiler generates errors.

Here is an example of a final method.
```
final void printStatistics() {
    ...
}
```

## Understanding Up Casting and Down Casting

You can cast an object to its superclass. This is known as up casting.
Java can up cast your objects implicitly. In general, you can up cast whenever
an "is-a-type-of" relationship exists between two classes.

In the previous example, you can cast `JoeyTribbiani` to `Friend` like this.

```
JoeyTribbiani joey = new JoeyTribbiani();
Friend friend = (JoeyTribbiani)joey;
```

In fact, you can leave the cast operator, because Java does it implicitly for you. 

Similarly, you can cast an object to its subclass. This known as down casting.
Down casting involves a type check and can throw a `ClassCastException`, if the
subclass is not a part of the instances class hierarchy.

In the Friends example, you can cast `Friend` to `ChandlerBing` like this.

```
Friend friend = new ChandlerBing();
ChandlerBing chandler = (ChandlerBing)friend;
```

But you cannot cast an instance of `PhoebeBuffay` to `ChandlerBing` like this.
Because `ChandlerBing` is not a part of the `PhoebeBuffay` class hierarchy.
```
Friend friend = new PhoebeBuffay();
ChandlerBing chandler = (ChandlerBing)friend;
```

Java provides a special operator called as instance of operator. It allows you
to determine whether an object is an instance of the specified class.

Here is the general form the instance of operator.
```
object instanceof Class
```

Here, the `object` represents the object you want to test. The instanceof operator
is actually a keyword. The `Class` represents the class the object should
be an instance of.

Here is an example.
```
if (friend instanceof ChandlerBing) {
    System.out.println("It is Chandler!");
}
else {
    System.out.println("I don't know who this is. Is it Monica?");
}
```