In the previous lectures you have learnt while and for statements. You can
program most situtations using these loop statements. Additionally, Java provides
another loop statement known as the do-while statement.

As you have seen, if the conditional expression controlling a loop statement
evaluates to `false` initially, then the body of the loop will not be executed
at all.

However, sometimes you might want to execute the body of a loop at least
once, even if the conditional expression is false to begin with. In such cases,
you can use the do-while statement provided by Java.

The do-while loop always executes its body at least once, because its conditional
expression is at the bottom of the loop.

The general form of the do-while statement is shown here.
```
do {
    // body
}
while (condition);

Each iteration of the do-while loop first executes the body of the loop and
then evaluates the conditional expression. If this expression is `true`, the
loop will repeat. Otherwise, the loop is terminated.

Here's an example of using a do-while statement in a menu driven program.

```
public class MenuUsingDoWhile {
    
    public static void main(String ... arguments) throws Exception {
        char choice;
        do {
            System.out.println(
                "\nThe valid choices are as follows.\n" +
                "1 - Pizza\n" +
                "2 - Biryani\n" +
                "3 - Fried Rice\n" +
                "4 - Burger\n" +
                "Any other number causes the program to exit.\n");
    
            System.out.print("What's on your mind, master Bruce? ");
            choice = (char)System.in.read();
            System.in.skip(10);
            
            switch(choice) {
                case '1':
                    System.out.println("Who is mood for some Joey's special?");
                    break;
                
                case '2':
                    System.out.println("A moment on the lips. Not sure about other items here, but Biryani surely stays forever on your hips!");
                    break;
                    
                case '3':
                    System.out.println("A fine choice, sire!");
                    break;
            
                case '4':
                    System.out.println("Sorry, we are out of burgers. Come back later.");
                    break;
                
                default:
                    System.out.println("Bye! See you again soon.");
            }
        }
        while ((choice >= '1') && (choice <= '4'));
    }
}

Here is a sample run produced by this program.

```
The valid choices are as follows.
1 - Pizza
2 - Biryani
3 - Fried Rice
4 - Burger
Any other number causes the program to exit.

What's on your mind, master Bruce? 4
Sorry, we are out of burgers. Come back later.

The valid choices are as follows.
1 - Pizza
2 - Biryani
3 - Fried Rice
4 - Burger
Any other number causes the program to exit.

What's on your mind, master Bruce? 3
A fine choice, sire!

The valid choices are as follows.
1 - Pizza
2 - Biryani
3 - Fried Rice
4 - Burger
Any other number causes the program to exit.

What's on your mind, master Bruce?
```

In the previous example, the do-while statement is used to display a menu and
serve accordingly. When the user enters an unknown choice, the program terminates.

Notice that characters are read from the keyboard using the `System.in.read()`
method. Whenever the user enters a choice, some extra characters are read by
your program. We call the `System.in.skip(10)` method to discard these characters.

Further, to deal with input errors we add the throws clause at the beginning of
the main method.

You will learn more about input/output and exceptions later in this course.
Don't worry, you don't have to understand these concepts right now.