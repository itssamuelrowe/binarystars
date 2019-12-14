## Extending Interfaces

You can organize your interfaces in a hierarchy just like classes.

An interface that you inherit is known as *parent interface*, or *base interface*,
or *superinterface*.

An interface which inherits is known as *child interface*, or *derived interface*,
or *subinterface*.


Imagine you have an interface that already has the behavior and constants that
another interface needs. You do not have to rewrite or copy your code to have the
same features in your interface. With inheritance, your interface automatically
receives the features from its superinterface. Basically, an interface becomes
a combination of its own features and all the features it inherits from the
interfaces above it in the hierarchy.

To inherit an interface, you simply specify the interface to inherit in the
definition of your interface using the extends clause. The general form of the
extends clause is shown here.

```
interface A extends B, C, D, ..., N {
}
```

Unlike a class inheritance, an interface can extend multiple interfaces at the
same time. In which case, it is a combination of all its features and the
features inherited by all the interfaces. You need to separate the
superinterfaces with a comma.

Here is an example where an interface inherits from multiple superinterfaces.

```
interface SingleClickListener {
    void handleSingleClick();
}

interface DoubleClickListener {
    void handleDoubleClick();
}

interface ClickListener extends SingleClickListener, DoubleClickListener {
}
```