+++
title = "Declaring Packages"
weight = 2
+++

To create a package you need to use the package statement at the beginning of
your source file.

Here is the general form of the package statement.

```
package qualifiedName;
```

Here, the `qualifiedName` represents the name you assigned your package.

Here is an example of a package statement.

```
package example;
```

The package statement should always be the very first statement in your source
file. The package statement creates a namespace identified by the qualified name
you specify. Any classes you create in that file will belong to this package.

If you skip the package statement, the classes are stored in the default
package, which is why you were able to create classes so far. The default
package has no name. The default package is usually not used in real life
applications. Most of the time, you will create your own packages.

Java uses folders, also known as directories, to represent packages on disk. For
example, your `.java` and `.class` files for the classes you declare in the
`example` package should be stored in the `example` directory. 
Remember that package names are case sensitive. Therefore, the directory names
must match the package name exactly.

In real-life applications, your source code is spread across many files. Any
number of source files can be a part of a package, as long as they all declare
the same package statement. The package statement specifies the package in which
the classes in your file belong to.