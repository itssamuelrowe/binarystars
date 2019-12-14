A method is a block of statements. You can give it a name. A method defines an
object's behavior, basically whatever an object is capable of performing.

You can call or invoke a method with its name. When you invoke a method, the
execution of your program branches to the body of that method. When the method is
finished, execution resumes from where the program branched, and the program
continues on to the next statement.

You have already used methods. For example, `print` and `println` are
methods declared in the `PrintStream` class.

# Advantages of Methods

The primary advantages of methods are as follows.
 * Methods improve the quality of your code. They make it more readable because
   you break your code into logical chunks.
 * You avoid duplicate code. Imagine you are writing an application that simulates
   an airplane, which requires primitive matrix operations such as addition,
   subtraction and multiplication. Without methods you would have to write these
   operations in several places. So whenever you see yourself writing the same
   code, it is a good idea to write a method.
 * You can implement polymorphism through methods. This is one of the most important
   features of methods.

## Creating Methods

Here is the general form of a method declaration.

```
returnType name(parameters) {
	statement1
    statement2
    ...
    statementN
}
```

The *return type* tells whether the method returns a value, or not. If so,
the type of the value it will return. You can use `void` to tell that your
method does not return any value.

The `main() method` does not return any value, this is why we declare its return type
as `void`.

You will learn about returning values later in this chapter.

The name of your method helps you call it.

The class body begins with a left brace (`{`) and ends with a right brace (`}`).
You can write any number of statements inside its body. In fact, you can leave
it empty.

## Naming Conventions for Methods

 * Begin method names with a lowercase letter. For example, `print`, `getName`,
  `setTitle` and `buffer`.
* If the method name consists of more than one word, capitalize every word,
  except the first word. For example, `toString`, `initializeCamera`, `launchRocket`
  and `parseInteger`.
* Try to begin your method names with verbs. The name of a method should indicate
  an action.

Here is an example of a program which has redundant statements. Apparently,
Harry and Hermione are on an adventure, trying to break into a mysterious tower.

```
public class MysteryTower {

	public static void main(String... arguments) {
		System.out.println("Harry Potter: Can you open this door?");
        System.out.println("Hermione Granger: Alohomora!");
        
		System.out.println("Harry Potter: Can you open this door?");
        System.out.println("Hermione Granger: Alohomora!");
        
		System.out.println("Harry Potter: Can you open this door?");
        System.out.println("Hermione Granger: Alohomora!");
        
        System.out.println("The door opens!");
	}
}
``

In this example, your program prints the same messages three times. But then
you end up writing the same statements over and over. Of course, you could
rewrite this program with a loop. Alternatively, you could use a method.

Here is another version of the previous example using a method.

```
public class MysteryTower {

	void openDoor() {
		System.out.println("Harry Potter: Can you open this door?");
        System.out.println("Hermione Granger: Alohomora!");
	}

	public static void main(String... arguments) {
		MysteryTower mysteryTower = new MysteryTower();
		MysteryTower.openDoor();
		MysteryTower.openDoor();
		MysteryTower.openDoor();
        
        System.out.println("The door opens!");
	}
}
```

A method should always be declared in a class. The order in which you
declare your methods does not matter. So in this example, you could write
the `openDoor()` method after the `main()` method, it would not matter. Your
program will execute the same.

```
public class MysteryTower {

	public static void main(String... arguments) {
		MysteryTower mysteryTower = new MysteryTower();
		MysteryTower.openDoor();
		MysteryTower.openDoor();
		MysteryTower.openDoor();
	}

	void openDoor() {
		System.out.println("Harry Potter: Can you open this door?");
        System.out.println("Hermione Granger: Alohomora!");
	}
}
```

As you can see, the `openDoor()` method is declared without the static modifier,
making it an instance method. Which means you need an instance of the `MysteryTower`
class before you can access it. Therefore, we create an instance of the `MysteryTower`
class and save a reference to it in the `mysteryTower` variable. Remember,
`MysteryTower` with an uppercase `M` and `mysteryTower` with a lowercase `m`
are two different identifiers.

Then, we call the `openDoor()` against the `MysteryTower` object three times.
Each time you call `openDoor()`, the control is transferred to it from the `main()`
method.

The two print statements in the `openDoor()` method are executed sequentially.
After which the control returns back to where the method was called.