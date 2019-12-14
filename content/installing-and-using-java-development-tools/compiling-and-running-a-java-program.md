+++
title = "Compiling and Running a Java Program"
weight = 4
+++

In this section you will learn to compile and run a Java program.

Java comes with several command-line tools you can run from your console.
The two most important are `javac`, the Java compiler used to compile a program,
and `java`, the Java Virtual Machine used to run your program. These
tools work essentially the same no matter what operating system you're
using.

You can compile a program from your console using the `javac` command.

Quickly, open your plain text editor such as Notepad. Make sure you don't use
text editors such as Microsoft Word.

Type the following program into a file and save it as `HelloWorld.java`. Remember
to save the file name with the case.

```
public class HelloWorld {

    public static void main(String... arguments) {
        System.out.println("Hello, world!");
    }
}
```

Save the file in any folder you wish.

Make sure you use the same case as shown. Otherwise, your may not be able
compile and run your program. For example, if you type `class` as `Class`,
the program won't work.

Alternatively, you can download the example programs from my repository.

To compile and run your program follow these instructions:
 * Open a console window.
 * Change the directory to where you saved your file using the `cd` command.
   In this example, I saved my program in `C:\examples`. To change the directory
   I will have to use `cd C:\examples`.
 * To compile your program, enter `javac HelloWorld.java`
 * If you typed the program correctly, the `javac` command won't display any
   messages. If the program contains any errors, error messages are displayed
   on your console.
 * If your program compiled successfully, the compiler would have created
   a `HelloWorld.class`. It contains the bytecode, which is the binary equivalent
   of your source code.
 * To run your program, enter `java HelloWorld`. This will display the messages
   `Hello, world!` on your console.