+++
title = "Working with the Import Statement"
weight = 5
+++

You have learnt how packages allow you to keep your classes organized. However,
as you have seen accessing classes from different packages require fully qualified
names, which means you have to type so much just to refere a class! For this reason,
Java provides the import statement.

The general form of the import statement is shown here.
```
import qualifiedName;
```

Here, the qualified name refers to the class which you want to import. A qualified
name can consist of any number of identifiers as long as they are separated by
the dot symbol.

The import statement basically allows you to access a class from a different
package without its fully qualified name. Once you import a class, you can refer
it directly, using only its name.

The import statement exists to make your life easier. In the background, the
classes are still referred by their fully qualified names.

Consider the following classes which we saw in the previous section.
```
package com.example;

public class Message {

    private String message;
    
    public Message(String message) {
        this.message = message;
    }

    public void print() {
        System.out.println(message);
    }
}
```

```
public class PackageDemo {
    
    public static void main(String ... arguments) {
        com.example.Message message = new com.example.Message("Hello, world!");
        message.print();
    }
}
```

You could rewrite the `PackageDemo` class like this using the import statement.
```
import com.example.Message;

public class PackageDemo {
    
    public static void main(String ... arguments) {
        Message message = new Message("Hello, world!");
        message.print();
    }
}
```

You always need to write the import statements immediately after the package
statement, if there is one. You cannot write the import statement after or
inside a class declaration.

Sometimes you import many classes from the same package, which means you will
have to write an import statement for each class. This is again cumbersome.
Java provides a solution to this problem: the wildcard import statement.

In such an import statement, you specify the package name followed by an asterisk.
Here is the general form of such a statement.
```
import level1.level2.*;
```

When you specify a package name followed by an asterisk, all the classes in
the package are imported.

Here is an example which demonstrates how you can import all the classes in
the `java.util` package.
```
import java.util.*;
```

There are two drawbacks with wildcard import statements.
    
    * It increases the time required to compile your program, especially if your
      source files import large packages. Since the classes are referred by
      their fully qualified names in the background, the bytecode generated
      is the same, with or without the wildcard import statements. In other words,
      wildcard import statements do not affect your runtime performance.
    
    * It clutters your local namespace, if multiple packages have classes
      with the same names. This forces you to use fully qualified class names.
      
      When you import multiple packages with a wildcard import, chances are two
      or more classes may have the same name. The import statement does not
      generate an error during such imports. Instead an error is generated when
      you try to refer to either one of them. In such cases, you can resolve
      the conflict by using a fully qualified name to indicate which class
      you are referring to.
      
For these reasons, we recommed you to use wildcard import statements with care.

All the standard classes in Java are bundled in the `java` package, which includes
other sub-packages. It includes a special package called `java.lang`. The classes
in this package are always implicitly imported to your source files. Many classes
such as `Object`, `Integer`, and `String` are defined in this package.