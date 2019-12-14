+++
title = "Working with Constructors and Inheritance"
weight = 4
+++

When you inherit a class, the constructors are not inherited. Because cnostructors
are not instance members. Which means each class should create its own constructors.
However, sometimes you may want to invoke the constructor of a superclass from
your subclass.

For example, to initialize the fields in a superclass you either need access to
them or invoke the constructor. The former technique is verbose and not recommended
because it violates the principles of encapsulation. Instead you can invoke the
superclass constructor.

## Invoking Superclass Constructors

A constructor can call the superclass constructor from a subclass. Java provides
special syntax for this purpose. You must use the `super` keyword with parenthesis.
This is useful when your subclass constructor requires some behavior which already
exists in superclass constructor.


Whenever you want invoke a supeclass constructor you can use the super keyword.

Here is the general form invoke a superclass constructor.

```
super(arguments);
```

Here, the arguments are the values you want to pass to your superclass constructor.

You need to follow these rules when calling a superclass constructor.

#### RULE 1 - You can call another constructor only in the very first statement of your constructor.

For example, this will not compile.

```
public HollywoodMovie(String title) {
    int i = 0;
    super(title, 0.0f, 0.0f);
}
```

You can call a superclass constructor only in the first statement. But in the above
example, a declaration statement is the first statement. This results in a
compile-time error.

#### RULE 2 - A constructor can call only one superclass constructor.

For example, this will not compile.

```
public SandalwoodMovie(String title) {
    super;
    super(title, 0.0f, 0.0f);
}
```

You can call only one superclass constructor. But in this example, the constructor
invokes two superclass constructors. This results in a compile-time error.

#### RULE 3 - You can either invoke another constructor or a superclass constructor, not both.

For example, the first constructor can call the second constructor. The
second constructor can call the third constructor.

```
public HollywoodMovie(String title) {
    super(title, 0.0f, 0.0f);
    this("Christopher Nolan");
}
```

You can call a superclass constructor or another constructor in your class.
But this constructor invokes both the constructors. This results in a compile-time
error.

This rule applies only when you explicitly invoke a superclass constructor. 
Because when you don't invoke the superclass constructor, Java automatically
invokes the default superclass constructor.

## Subclass Instance vs Superclass Instance

You have already seen how the `this` keyword works. It provides a reference to
the current instance. You can use it distinguish between a local variable and an
instance variable with the same name.

Sometimes you may want to distinguish between a subclass instance member and
a superclass instance member. In such cases, you use the `super` keyword.
It is a reference to the superclass directly above the current subclass in the
hierarchy.

A very common place where the `super` keyword is used is when you override
a method and you want to invoke the method defined in the superclass.

Here is an example, where the superclass reference is used.
```
class A {

    public void printMessage() {
        System.out.println("This is the method defined in the superclass.");
    }
}

class B extends A {

    @Override
    public void printMessage() {
        super.printMessage();
        System.out.println("This is the method defined the subclass.");
    }
}
```

Another bizzare case is when your subclass and superclass have fields with
the same name. Yes, this is possible because because fields and local variables
have different scopes. You should remember that fields cannot be overridden like
methods because fields are not polymorphic. In such cases, the subclass field is
basically hiding or shadowing the field declared in the superclass.

You should never shadow fields because it makes your code less readable.
Although this does not matter, if the fields are private in the first place.
Because private fields are not inherited.

In any case, you can specify which field you are accessing using the compile time
type of the expression. Another technique to distinguish the fields is to use
the superclass reference.

Here is an example.
```
class A {

    public String message = "This is the superclass message";
}

class B {

    public String message = "This is the subclass message";

    public void printMessage() {
        // Print the message defined in the superclass.
        System.out.println(super.message);
        // Print the message defined in this class.
        System.out.println(message);
    }
}
```