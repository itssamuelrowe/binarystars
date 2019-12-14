A *parameter* is a value that you can send to a method. Parameters allow a
method to be generalized. In other words, such methods can operate on a
variety of data and work differently based on different arguments.

It is important to understand the difference between parameters and arguments.
A parameter is a variable defined by a method that receives a value when the
method is invoked. Whereas, an argument is a value that is passed to a method
when it is invoked.

## Declaring Parameters

You must list your parameters when you declare your method. The parameters are
listed in the parentheses after your methods name. Every parameter should
have both type and name, just like declaring a local variable.

You can pass values to your method when you call it. List your values in the
parentheses after your methods name.

Consider the following example.

```
void square() {
    System.out.println(7 * 7);
}
```

The `square()` method prints the square of `7`. Although this method works
perfectly, it is very limited. However, if you modify the method to accept a
parameter, you can make it more useful and flexible.

```
void square(int number) {
    int result = number * number;
    System.out.println(result);
}
```

You can use a parameter like any other local variable. Its value is initialized
with the value you pass.

For example, you can call `square` like this.
```
square(5)
```

If you need more than one parameter, you must separate them with commas.

Here is an example.

```
void createUser(String name, int age) {
    ...
}
```

You can call `createUser` like this:
```
createUser("Sherlock Holmes", 24);
```

If your method needs no parameters, leave the parentheses empty.

Here is an example.
```
void collect() {
    ...
}
```

You can call `collect` like this:
```
collect()
```

## Understanding Scope of Parameters

The parameters of your method exists only within the method. You can't access it
outside your method.

```
public class Calculator {

    public static void main(String[] arguments) {
        int x = 10;
        int y = 20;
        int result;

        result = add(x, y);

        System.out.println(x + " + " + y + " = " + result);
    }

    public static int add(int x, int y) {
        return x + y;
    }
}
```

In 'main`, we declared two variables named `x` and `y`. We call `add()` to
add the `x` and `y`.

The `add` method accepts two parameters named `x` and `y`.

The local variables in `main` and the parameters in `add` have the same names.
Compile this program. The compiler does not complain.

But why? Shouldn't the compiler generate errors if we declare variables with
the same name?

As we told earlier, parameters exist only within the method they are declared.
And local variables exist only within the block they are declared. This is why
the compiler does not generate any error.

## Understanding Pass-By-Value

When you pass a primitive value, such as integers, characters and decimals,
as an argument to a method, the method receives a copy of the value.

Similarly, when you pass a variable that contains a primitive value as an
argument to a method, the method receives a copy of the variable's value, not
the variable itself.

This technique is called pass-by-value. This technique is applied when you pass
primitive values, such as integers, characters, and decimals.

Therefore, when you pass an argument through a variable, and if the method
changes the value it received through the parameter, it is not reflected in
the original variable that was passed to the method.

Consider the following example.

```
public class PassByValueDemo {

    public static void main(String... arguments) {
        int number = 7;
        System.out.println("[before] number in main() = " + number);
        changeValue(number);
        System.out.println("[after] number in main() = " + number);
    }
    
    public static void changeValue(int anotherNumber) {
        anotherNumber = 19;
        System.out.println("anotherNumber in changeValue() = " + anotherNumber);
    }
}
```

The output of the example is shown here.

```
[before] number in main() = 7
number in changeValue() = 19
[after] number in main() = 7
```

In this example, a variable named `number` is assigned `7`. Its value is
printed on the console. Then the `changeValue()` method is invoked with
`number` as its argument.

`changeValue()` receives the value as the parameter named `anotherNumber`.
It modifies the value of `anotherNumber` to `19` and prints out the value stored
in it.

When the `changeValue()` method terminates, the control is again transferred to
`main()`, where the current value of `number` is printed. Since the
`changeValue()` was invoked with a copy of the value, the `number` variable
remains unchanged even though `changeValue()` modified its parameter.

## Understanding Pass-By-Reference

When you pass a reference value, such as objects and arrays, as an argument to
a method, the method receives a copy of the reference. In other words, the object
itself is not copied when you pass it as an argument, only its reference is copied.

Similarly, when you pass a variable that contains a reference to an object as an
argument to a method, the method receives a copy of the reference, not the the
variable itself.

This technique is called pass-by-reference. It is applied when you pass reference
values, such as objects and arrays.

Therefore, if a method changes the reference it received through the parameter,
it is not reflected in the original variable that was passed to the method.

However, if the object is modified through the reference, then the change is
reflected in the object. Because both the argument and the parameter refer to
the same object, and not separate copies of the object.

Consider the following example.

```
class Square {

    int side;
}

public class PassByReferenceDemo {

    public static void main(String... arguments) {
        Square square = new Square();
        square.side = 5;
        
        System.out.println("[before] square in main contains side = " + square.side);
        changeValue(square);
        System.out.println("[after] square in main contains side = " + square.side);
    }
    
    public static void changeValue(Square referenceToSquare) {
        referenceToSquare.side = 7;
        System.out.println("referenceToSquare in changeValue contains side = " + referenceToSquare.side);
    }
}
```

The output of this example is shown here.

```
[before] square in main contains side = 5
referenceToSquare in changeValue contains side = 7
[after] square in main contains side = 7
```

In this example, a variable named `square` is assigned an instance of the `Square`
class. The value of the `side` field contained in the `square` object is assigned
`5`. It is then printed on the console. Then the `changeValue()` method is invoked
with `square` as its argument. Remember, the reference to the `square` object is
copied, not the object itself.

`changeValue()` receives the reference as the parameter named `referenceToSquare`.
It modifies the value of `side` contained in the `Square` object to `7`. After
which it prints out the value stored in it.

When the `changeValue()` method terminates, the control is again transferred to
`main()`, where the current value of `side` is printed. Since the
`changeValue()` was invoked with a copy of the reference, the `square` object
has been changed!