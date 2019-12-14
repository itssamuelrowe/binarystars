+++
title = "Creating Anonymous Inner Classes"
weight = 2
+++

Sometimes an inner class is used only once by the outer class. In such
cases, you can remove the declaration and make the class anonymous.

An anonymous class is a class without a name, extends clause and implements clause.
It is always used with the new operator.

Remember that abstract classes and interfaces cannot be instantiated directly.
With anonymous classes you can provide a class body while you instantiate it.

Consider the following example.

```java
interface OnClickListener {
    void handleClick();
}

public class InnerClassDemo {
    private static class MyOnClickListener implements OnClickListener {

        @Override
        public void handleClick() {
            System.out.println("The button was clicked");
        }
    }

    public static void main(String... arguments) {
        OnClickListener listener = new MyOnClickListener();
        listener.handleClick();
    }
}
```

As you can see, `MyOnClickListener` class is used only once. Therefore, it is
a good idea to rewrite it as an anonymous class.

```java
interface OnClickListener {
    void handleClick();
}

public class InnerClassDemo {
    
    public static void main(String... arguments) {
        OnClickListener listener = new OnClickListener() {

            @Override
            public void handleClick() {
                System.out.println("The button was clicked");
            }
        };
        listener.handleClick();
    }
}
```

In Java, the new operator returns an object. Basically, the new operator in
this example creates an object of an anonymous class that implements the
`OnClickListener` interface, which overrides the `handleClick()` method.