You can create a class inside another class. An inner class exists to help the
class within which it is declared. It is also known as a nested class.

Here is the general form of an inner class.

```
modifiers class OuterClass {

    modifiers class InnerClass {
    }
}
```

Inner classes are useful in several situations. 

An inner class is similar to a helper class. But it can access the private
members of the outer class, which a helper class cannot. Yes, this is possible
because the private members of the outer class are accessible within its body,
and the inner class exists within the body of the outer class.

You can declare an inner class as static, if you want to access only the static
fields. In order to access instance members, the inner class should be an
instance member itself.

If only one class is depedent on another class, is a good idea to define the
other class inside the dependent class. This keeps your code organized.
Further, the relationship between the classes is more clear.

Here is an example of an inner class.

```
public class HelloWorld {
    
    private class Message {
        
        Message() {
            System.out.println("The inner class says, 'Hello world!'");
        }
    }
    
    public void printMessage() {
        new Message();
    }
    
    public static void main() {
        HelloWorld world = new HelloWorld();
        world.printMessage();
    }
}
```

In order to access the inner class, you need to create an instance of the outer
class. This is because the `Message` class was declared as an instance member.
Which means, only other instance members can access this class.

This is why, we first create an instance of the `HelloWorld` class. Then we
invoke the `printMessage` method which takes care of creating an instance
of the `Message` class.

The message is printed in the constructor of the `Message` class. The instance
is of no further use. This is why we did not save a reference to it.

In fact, you could have created an instance of the `Message` class from the
`main()` method like this.
```
world.Message message = new world.Message();
```

Notice that a reference to the `HelloWorld` object is required to access the
Message class and its constructor.