You can extract characters from strings in a number of ways. We discuss about
each technique in this section.

Internally, strings store characters in an array. However, you cannot access the
characters of the string using the array subscript operator. But many methods
in the `String` class require indexes to operate. Just like array, string indexes
are zero based. So it would help you to understand strings better if you think of
them as arrays. 

You can extract a single character from a String using the `charAt()` method.
It accepts an index of the character you want to retrieve. You cannot specify
negative values. It throws a `StringIndexOutOfBoundsException` if the index
is invalid.

Here is the declaration of the `chartAt()` method.

```
char charAt(int where)
```

It returns the character at the specified index.

Here is an example.

```
String color = "Neon";
char c = color.charAt(2);
System.out.println(c);
```

This snipet prints the following output.
```
o
```

You can retrieve a range of characters at a time using the `getChars()` method.

Here is the declaration of the `getChars()` method.
```
void getChars(int startIndex, int stopIndex, char[] destination, int destinationIndex)
```

Here, the `startIndex` specifies the index from which the copying begins. It is
inclusive.

The `stopIndex` specifies the index at which the copying ends. This index is exclusive,
which means the character at this index is not copied. 

The characters are copied to the `destination` array you specify. The characters
are copied into the destination array beginning at the index specified by
`destinationIndex`. You need to make sure that the destination array is large
enough to store the range of characters.

Here is an example which copies a range of characters.

```
public class ExtractRangeOfCharactersDemo {

    public static void main(String ... arguments) {
        String message = "How you doin?";
        int startIndex = 4;
        int stopIndex = 7;
        char[] destination = new char[3];
        message.getChars(startIndex, stopIndex, destination, 0);
        
        String message2 = new String(destination);
        System.out.println(message2);
    }
}
```

This example prints the following.
```
you
```

If you want to convert all the characters in your string into a character array,
invoke the `toCharArray()` method. It returns an array of characters from your
string.

The declaration of the `toCharArray()` method is shown here.
```
char[] toCharArray()
```

You can use the `getChars()` method to perform the same operation, except
`getChars()` makes you write more code.

--------------------------------------------------------------------------------

The `substring()` method allows you to extract a region of your string, usually
referred as substring. 

The declaration of this method is shown here.
```
String substring(int index)
```

Here, the index indicates the index from which the substring is extracted.
The substring begins from the specified index and extends to the end of the string.

Here is an example of the `substring()` method.
```
String lastName = "Nikola Tesla".substring(7);
System.out.println(lastName);
```

This example prints the following output.
```
Tesla
```

An overloaded version of the `substring()` method allows you to extract a 
range of characters from the string.

Here is the declaration of the `substring()` method.
```
String substring(int startIndex, int stopIndex)
```

Here the `startIndex` specifies the start index of the substring and the
`stopIndex` specifies the end index of the substring. The `startIndex` is
inclusive, whereas, the `stopIndex` is exclusive.

Here is an example of the overloaded version of the `substring()` method.
```
String name = "Nikola Tesla".substring(2, 6);
System.out.println(name);
```

This example prints the following output.
```
kola
```