+++
title = "Working with Classes"
weight = 1
+++

In the real world, you wll find many objects of the same kind. There are
thousands of bikes with the same make and model. Each of these bikes was built
with the same blueprint.

A class is a blueprint from which you create objects.

The most important thing to understand about a class is that it defines a new
data type. Once defined, this new type can be used to create instances.
In other words, a class is a blueprint or a template for an object, and an
object is an instance of a class. Because an object is an instance of a class,
you will often see the two words object and instance used interchangeably.

You should declare a class with a name and a body. Here is the general form of
a class declaration.

```
class Name {

    /* Fields */
    /* Initializers */
    /* Constructors */
    /* Methods */
    /* Classes, Interfaces, and Enumerations */
}
```

The class body begins with a left brace (`{`) and ends with a right brace (`}`).

It can contain the following elements.
 * **Constructors**
   A constructor is a block of code that runs whenever you create an instance.
   It initializes new instances.

 * **Initializers**
   An initializer is a block of code that runs whenever you create an instance.
   It initializes new instances. Initializers are similar to constructors,
   except initializers cannot accept parameters.

 * **Fields**
   A field is a variable declared inside a class body and outside a method body.
   A field provides the state of the class and its instances.

   There are two types of fields, instance variables and static variables.
   
   When you declare a field inside a class, outside a method, and without
   the `static` keyword it is an instance variable.

   Similarly, when you declare a field inside a class, outside a method, and
   with the `static` keyword it is a static variable. You will learn about static
   variables later in this chapter.

 * **Methods**
   A method is a block of code. It defines *a behavior* of the class and its
   instances.

 * **Classes, Interfaces, and Enumerations**
   A class can include the declarations of other classes, interfaces, and
   enumerations.

Don't worry if you don't understand these concepts. You will learn them
in detail later in the following chapters.

The order in which you write your class members does not matter, except for
initializers. But follow a uniform order. So you will know where to find your
members.

The fields, methods, classes, and interfaces, that is, the entities that you declare
inside your class are known as its **members**.

# Working with Fields

The general form of a field is shown here.

```
modifiers type identifier;
```

You can declare fields like any other variable. You can optionally specify
*modifiers*.

The modifiers tell the compiler additional characteristics of the field such as
visibility, mutability, etc.

Basically, there are seven modifiers you can use when you declare a field.
    * final
    * private
    * public
    * protected
    * static
    * transient
    * volatile

Each modifier is a keyword. We will be learning about all the modifiers, except
transient and volatile keywords, in this chapter.

Here is an example of a class called `Superhero`.

```
public class Superhero {

    String name;

    String gender;

    int strength;

    int speed;

    String intelligence;
}
```

This class definition contains five variables. Because these variables are not
defined inside a method without the `static` keyword, they are instance variables.

In this example, the `name` field holds the name of the superhero.
For example, `Batman`.

The `gender` field holds the gender of the superhero. For example, it would be `Female`
for Wonder Woman.

The `strength` field represents the muscular strength of the superhero, ranging
from 1 to 10. For example, The Presence would have a perfect 10.

The `speed` field represents the speed of the superhero, ranging from 1 to 10.
For example, you guessed it, The Flash would have a perfect 10.

The `intelligence` fields represents the intellect of the superhero. For example,
Batman would be considered `very intelligent`, just behind Lex Luthor, a supervillan.

It is important to remember that a class declaration only creates a blueprint.
It does not create an actual object. Thus, the previous example does not create
any object.

To actually create a `Superhero` object, you should use the `new` keyword, which is
an operator.

## Working with the New Operator

The general form of the `new` operator to create an instance of a class is
shown here.

```
new Class()
```

Here the `Class` represents the name of the class whose instance you want to
create. You will learn the significance of the parenthesis when you learn
about constructors.

You can use the `new` operator to create other kinds of objects, such as arrays.
You will learn the other forms of the `new` operator later in the course.

To create an instance of the Superhero class, you would write something like this.

```
Superhero superman = new Superhero();
```

In this example, we created a variable called `superman` of type `Superhero`.
Then we created an instance of `Superhero` and assigned its reference to the
variable `superman`. A reference is important to write and read the values stored
in an object.

You should always remember that each instance contains its own copy of
instance variables. Thus, every Superhero object will contain its own copies of
name, gender, strength, speed and intelligence. This is a very important concept
you need to remember.

Here is an example where two Superhero objects are created.

```
Superhero superman = new Superhero();
Superhero batman = new Superhero();
```

In this example, `superman` object has its own copies of name, gender, strength,
speed, and intelligence. If you modified any of these fields it would not affect
the values stored in the `batman` object. Because each `Superhero` object contains
its own copies of the `Superhero` fields.

To access an instance variable, you can use the dot (`.`) operator. The dot
operator links the reference of the object with the instance variable.

For example, to assign `Batman` to the `name` instance variable contained in
the `batman` object, you can write the following statement.

```
batman.name = "Batman";
```

Here, the `batman` variable contains the reference to a `Superhero` object.
`name` indicates the instance variable to modify.

The dot operator is a binary operator. Obviously, the dot operator always returns
a value. Accessing instance variables with it is an expression. In fact, both
the operands of the dot operator are expressions. This means that you can chain
instance variable access. You will see chaining instance variable access later
in the course.

Here is the complete Superhero program.

```
public class Superhero {

    String name;

    String gender;

    int strength;

    int speed;

    String intelligence;

    public static void main(String... arguments) {
        /* Create the Superhero objects. */

        Superhero superman = new Superhero();
        superman.name = "Superman";
        superman.gender = "Male";
        superman.strength = 9;
        superman.speed = 9;
        superman.intelligence = "Very intelligent";

        Superhero batman = new Superhero();
        batman.name = "Batman";
        batman.gender = "Male";
        batman.strength = 6;
        batman.speed = 6;
        batman.intelligence = "Very intelligent";

        /* Print the values contained in the instance variables. */

        System.out.println("Name\t\t:\t" + superman.name);
        System.out.println("Gender\t\t:\t" + superman.gender);
        System.out.println("Strength\t:\t" + superman.strength);
        System.out.println("Speed\t\t:\t" + superman.speed);
        System.out.println("Intelligence\t:\t" + superman.intelligence);

        System.out.println();

        System.out.println("Name\t\t:\t" + batman.name);
        System.out.println("Gender\t\t:\t" + batman.gender);
        System.out.println("Strength\t:\t" + batman.strength);
        System.out.println("Speed\t\t:\t" + batman.speed);
        System.out.println("Intelligence\t:\t" + batman.intelligence);
    }
}
```

The output produced by the Superhero program is shown here.

```
Name            :       Superman
Gender          :       Male
Strength        :       9
Speed           :       9
Intelligence    :       Very intelligent

Name            :       Batman
Gender          :       Male
Strength        :       6
Speed           :       6
Intelligence    :       Very intelligent
```

## Understanding Object References

When you declare a variable with a class as its type, you are basically creating
a reference variable. If you remember from chapter 4, this is because classes
are reference types, not primitive types.

Reference variables are quite different from primitive variables.

For example, what do you think the following code segment performs?
```
Superhero shazamKid = new Superhero();
Superhero darlaDudley = shazamKid;
```

You might think that `darlaDudley` is being assigned a copy of new Superhero object.
In other words, you might think that `shazamKid` and `darlaDudley` refer to
two separate and distinct objects. However, this is not true.

If you ran this code, `shazamKid` and `darlaDudley` will both refer to the same
object. The assignment of `shazamKid` to `darlaDudley` did not create any new
copy of the original object. It simply makes `darlaDudley` refer to the same
object that `shazamKid` references.

Thus, any changes made to the object through `darlaDudley` will affect the
original object and the changes will reflect through `shazamKid`.