+++
title = "Understanding Strings"
weight = 1
+++

In Java, strings are not primitive types. The string is implemented by the `String`
class defined in the `java.lang` package. All strings are objects, but Java treats
strings specially.

A string is a sequence of characters. You can create a string by enclosing your
text in double quotes. The character sequence along with the double quotes
form a string literal.

Unlike many other programming languages, string are not arrays of characters.
Internally the String class stores the characters in an array, a detail which
you can safely ignore. But you always need to perceive strings as objects and
not arrays.

So far you have seen only one way to create a string object: to use the string
literal. However, the String class exposes a number of constructors, which allow
you to create strings in many ways.

You can perform various operations with strings, such as comparing two strings,
searching for substrings, concatenating two strings, and so on.

In Java, a string object is immutable, which means you cannot modify it once
you create it. In other words, once a string object is created, you cannot change
its characters. You can only derive a new string which is a modified version of
the original string. At first, this may seem to be a serious restriction. However,
immutable strings make your life easier. You can still perform all types of
string operations. Immutable strings are more efficient than mutable strings.

Java provides other mechanisms which allow you to derive modified versions of a
string. Each time you derive a new version of the string, you are creating a
new string object. The original string is always left as it is. 

If you have to make many changes to a string, deriving a new string for each
change is not efficient. For such situtations, Java provides two classes:
StringBuffer and StringBuilder. Both these classes internally represent strings
as arrays. So whatever changes you make will be quick and efficient. Once you are
satisfied with the changes, these classes allow you to derive an immutable string.
After which, you can use the string as usual.

The String, StringBuffer, and StringBuilder classes are defined in the `java.lang`
package. Therefore, all these classes are available to your programs automatically.
All the three classes implement the `CharSequence` interface, which means
most operations you find in strings are found in the other two classes, too.

Before we continue, here is a summary of strings.

 * Strings can include escape sequences. An escape sequence allows you to represent
  a special character which you would not be able to type with your keyboard. 
  It is written with a backward slash followed by a letter.
  
Here is the list of all the escape sequences availablen in Java.
+---------------------+-----------------+
| Escape Sequence     | Description     |
|---------------------+-----------------|
| \n                  | Newline         |
| \t                  | Tab             |
| \b                  | Backspace       |
| \r                  | Carriage Return |
| \f                  | Form feed       |
| \'                  | Apostrophe      |
| \"                  | Quotation mark  |
| \\                  | Backslash       |
+---------------------+-----------------+

 * Strings are objects and characters are primitive values. You enclose a string
  literal in double quotes, whereas characters are enclosed in single quotes.
  A string can contain zero or more characters, even if a string contains a single
  character within double quotes, it does not become a character.
  For example "S" is a string and 'N' is a character.

 * Strings are an important part of programming languages, therefore Java treats
   strings specially. In fact, strings support many special syntax. For example,
   string objects are created from string literals. However, you can use
   the constructors of the String class for more flexbility. You will learn
   about these constructors in the next section.

 * You can combine, or concatenate, strings using the concatenation operator (`+`).
   You can combine strings with other values, in which case Java automatically
   converts the value to a string for you. In the case of objects, the `toString()`
   method is first invoked to derive a string representation.
   
   Here is an example of the concatenation operator.

```
String firstPart = "Hello, ";
String secondPart = "world!";
String message = firstPart + secondPart;
```

 * Java offers a wrapper class for each primitive type. These wrapper
   classes allow you to convert a string to a corresponding primitive value.
   You can do this with the `parse*()` method these classes expose.

   Here is an example of how you can convert a string to an integer.
```
String text = "2000";
int year = Integer.parseInt(text);
```

    This example converts the string which contains "2000" to its equivalent integer
    value, which is 2000. However, if you specify an invalid text these methods
    throw `NumberFormatException`.

