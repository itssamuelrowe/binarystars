You cannot compare two strings for equality using the equality operator (`==`).
Remember strings are objects therefore you need to use the `equals()` method
to compare two strings for equality.

The declaration of the `equals` method is shown here.
```
boolean equals(Object other)
```

It returns `true` if both the strings contain the same characters in the same
order; `false` otherwise. You need to remember that this method is case sensistive.
For example, if you compare "Batman" and "batman" for equality, it would return `false`.

Here is an example which demonstrates how you can compare two strings for
equality.

``
String string1 = "Joker";
String string2 = "Harley Quinn";
if (string1.equals(string2)) {
    ...
}
```

You can compare two strings for equality without considering case. For this,
you need to invoke the equalsIgnoreCase() method.

```
boolean equalsIgnoreCase(String other)
```

It returns `true` if both the strings contain the same characters in the same
order; `false` otherwise. You need to remember that this method is case insensistive.
For example, if you compare "Camel" and "camel" for equality, it would return `true`.

Here is an example which demonstrates how you can compare two strings for
equality.

``
String string1 = "Poison Ivy";
String string2 = "poison ivy";
if (string1.equalsIgnoreCase(string2)) {
    ...
}
```

--------------------------------------------------------------------------------

You can compare a region inside your string with the region of another string.
You can invoke the regionMatches() method for this.

Here is the declaration of the `regionMatches()` method.
```
boolean regionMatches(int startIndex, String other, int otherStartIndex, int count)
```

The `startIndex` specifies the index at which the region begins for the string
object against which the method is invoked.

`other` represents the other string to compare. The `otherIndex` indicates the
index at which the region begins for the other string.

The `count` parameter indicates the number of characters in both the regions.
You need to carefully specify this parameter.

You can force `regionMatches()` method to ignore case. For this invoke the
overloaded version of the `regionMatches()`.
```
boolean regionMatches(boolean ignoreCase, int startIndex, String other,
    int otherStartIndex, int count)
```

The `ignoreCase` boolean parameter indicates whether the method should ignore
case when comparing, or not.

--------------------------------------------------------------------------------

You can determine if a string starts with a substring using the startsWith()
method. It returns true if a string starts with the specified substring; `false`
otherwise.

Here is the declaration of the `startsWith()` method.

```
boolean startsWith(String sequence)
````

Further, you can specify from which index `startsWith()` begins comparing.
An overloaded version of the `startsWith()` method accepts the starting index.
Here is the declaration of this method.
```
boolean startsWith(String sequence, int startIndex)
```

Here, the `startIndex` specifies the index applies to the string object against
which the method is invoked. It indicates the index from where the comparison is
started.

Similarly, you can determine if a string ends with a substring using the endsWith()
method. It returns `false` if a string ends with the specified substring; `false`
otherwise.

Here is the declaration of the `endsWith()` method.
```
boolean endsWith(String sequence)
```

Here is an example which demonstrates these methods.
```
String superhero = "Swamp Thing";
System.out.println(superhero.startsWith("Swam"));
System.out.println(superhero.endsWith("ing"));
System.out.println(superhero.startsWith("Thing", 5));
```

This example prints `true` three times.

--------------------------------------------------------------------------------

Imagine you are sorting an array of strings. How can you determine whether one
string is greater than the other? So far you have learnt about methods that only
help you determine whether they are identical. In order to compare strings
for relativity, you need to use the `compareTo()` method.

The `compareTo()` method compares two strings lexicographically, which means
a A is lesser B, B is lesser than C and so on. For example, A is lesser than Z
and Y is greater than M. In this logic, lowercase letters are always greater
than uppercase letters.

The declaration of the `compareTo()` method is shown here.
```
int compareTo(String other)
```
It returns a negative number if the current string object is lesser than the
specified string.
It returns a positive number if the current string object is greater than the
specified string.
It returns zero when both the strings are equal.

Here is an example, which determines if a string is greater than the other.
```
```

This program generate the following output.
```
Yatch is greater than Dragon.
```

As mentioned previously, the `compareTo()` method is case sensitive. For case
insensistive comparison you need to invoke the `compareToIgnoreCase()` method.

The declaration of the `compareToIgnoreCase()` method is shown here.
```
int compareToIgnoreCase(String other)
```