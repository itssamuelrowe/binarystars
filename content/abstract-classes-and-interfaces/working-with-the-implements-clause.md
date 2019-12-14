Once you define an interface, any number of classes can implement it.

In order to implement an implement an interface, you need to use the implements
clause in your class declaration. After which, you need to implement the methods
declared in the interface.

The general form of the implements clause is shown here.
```
class name extends superclass
    implements interface1, interface2, ..., interfaceN {
    ...
}
```
class classname [extends superclass] [implements interface [,interface...]] {

Here the extends clause is optional. In other words, you can implement interfaces
without inheriting any superclass.

Unlike inheritance, where a class inherits only one superclass, you can include
any number of interfaces when you implement it. In other words, you can specify
multiple interfaces in the implements clause. Each interface name should be
separated by a comma. Your class must implement the combination of all the behavior
included from the interfaces.

Your class needs to override all the methods declared in the interfaces mentioned
in the implements clause. In fact, if your class inherits methods from a superclass
which have the same signature as the methods declared in the interfaces, you do
not have to implement them.

An abstract class can implement interfaces, too. Unlike normal classes,
an abstract class can skip methods declared in an interface. In which case,
a subclass of the abstract class is required to implement it.

Here is an example example class which implements the `ShoppingList` interface
shown in the previous lecture.

```
class ConsoleShoppingList implements ShoppingList {

    @Override
    public void addItem(String item) {
        System.out.println("[+] " + item);
    }

    @Override
    public void removeItem(String item) {
        System.out.println("[-] " + item);
    }
}
```

The example shown here implements the `ShoppingList` interface.
Because interfaces provide nothing but abstract methods, you must implement
them in your class with the same signatures declared in the interface.

You should note that the methods declared in the interface are marked as
`public` in `ConsoleShoppingList`. This is required because the methods
in an interface are always public, whether you explicitly mark it or not.

You can create additional members other than what is declared in the interfaces,
like how you would in a normal class.


When you implement multiple interfaces, you may encounter conflicts. What happens
if two interfaces define the same method? You need to resolve the confliction in
one of the following ways.
    * If the methods have the same signature, you implement one method in
      your class for the both the declarations. The implementation should satisfy
      both the interfaces.
    * If the methods have the same signature but different return types, you
      cannot create a method that satisfies both. You need to remember that the
      return type is not a part of the signature. In such cases, you cannot
      implement both the interfaces in the same class. You need to think more
      carefully about your design.
      
## Using Interfaces as Variable Types

You can declare variables of an interface type instead of a class type.
Such a variable can reference any class instance that implements the interface.
When you invoke a method through the reference, the correct version of the method
will be called. This is done through dynamic method dispatch which determines
which version of the method to invoke at runtime. This is an important feature
of interfaces.

Here is an example that demonstrates using interface as a variable type.

```
public class ShoppingListDemo {
    
    public static void main(String ... arguments) {
        ShoppingList list = new ConsoleShoppingList();
        list.addItem("Butter");
        list.addItem("Jam");
        list.addItem("Bread");
        list.addItem("Sunflower Oil");
        list.removeItem("Jam");
    }
}
```

The output of this example is shown here.

```
[+] Butter
[+] Jam
[+] Bread
[+] Sunflower Oil
[-] Jam
```

Even though the instance may contain other methods, you can access only the
methods declared in the interface. Because the variable has only the knowledge
of the methods declared in the interface. One exception to this rule is that
you can access all the members of the `Object` class.