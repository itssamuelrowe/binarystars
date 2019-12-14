+++
title = "Understanding Identifiers"
weight = 2
+++

Identifiers are the names you give to variables, methods, classes, interfaces, and
enumerations. Unlike literals, identifiers only help you reference something.

The program shown in the [first example](/academy/book/java-programming-language/the-hello-world-program)
uses seven identifiers.
    * `Hello`
    * `main`
    * `String`
    * `arguments`
    * `System`
    * `out`
    * `println`

* Identifiers are case sensitive. For example, `ArrayList` with uppercase a and `arrayList` with lowercase a are two different identifiers.
* Identifiers may contain uppercase or lowercase letters, numerals,
  underscore characters `_`, and dollar symbols `$`.
* Identifiers must begin with a letter or an underscore. For example, `f07` is a valid
  identifier, but `7feb` isn't. Because it begins with a numeral.
* You can't use a *keyword* as an identifier. For example, `double` isn't a valid
  identifier.
* You have to avoid using dollar symbols in identifiers.

Here's an example of valid identifiers.
```
helloWorld
__student
Object
STRING
invoke123
$person
i
x1010
```

Here's an example of invalid identifiers.
```
void /* void is a keyword. You can't use a keyword as an identifier. */
hello world /* An identifier can't have spaces. */
3dCube /* An identifier can't begin with a numeral. */
a*a /* An identifier can't have symbols. */
```