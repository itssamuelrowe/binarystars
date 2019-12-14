> This section describes Unicode and how Java deals with it. It is a difficult
> concept to grasp. You can safely skip this section for now. You can come back
> when you are comfortable with Java.

To work with characters in a computer, you need the following:
    * Character Repertoire
    * Character Set
    * Character Encoding

Don't worry if you find these words scary. You'll easily understand them.
We have simplified their explanations.

### Understanding Characters Repertoire

A *character repertoire* is a collection of characters your computer can
work with. For example, a character repertoire may include letters, digits,
and symbols from Kannada, English, Tamil, Hindi, and Telugu.

### Understanding Character Set

Computers understand only numbers. So they store letters and other characters
by assigning a number for each one. These numbers are known as *codepoints*.

When a computer stores a character, it doesn’t really know the difference
between `A` and `B`. However, it knows the difference between `65` and `66`.
Internally, computers use the number `65` as the *codepoint* to represent `A`
and `66` for `B`.

In fact, all letters, digits, and symbols have codepoints. The codepoints given
to characters are collectively known as *character set* or *charset*.

When you store `'A'` in a `char` variable, you actually store the value `65` in
it. Which means, the `char` type is really an integer type.

Here's an example which prints the codepoints of A, B, C, D, E, and F.
```
public class CodePointsExample {

    public static void main(String[] arguments) {
        System.out.println((int)'A');
        System.out.println((int)'B');
        System.out.println((int)'C');
        System.out.println((int)'D');
        System.out.println((int)'E');
        System.out.println((int)'F');
    }
}
```

### Understanding Character Encoding

Finally, your computer stores your codepoints in a sequence of 1s and 0s.
This binary representation is called as *character encoding*.

## History of Unicode

There were hundreds of different character encodings before Unicode was
invented. The other character encodings were limited. They did not cover
all the languages of the world.

The *Unicode Standard* provides a codepoint for every character, no matter
what platform, device, application or language. It is used in all modern
software.

Unicode is a very popular character encoding standard. Many well known companies
such as Microsoft, Google and Oracle use Unicode. In fact, you are using Unicode
already.

Unicode was actually designed to *encode* characters in 2 bytes. This is why
`char` in Java uses 2 bytes.

Only 65,536 characters can be encoded with 16 bits. You can't represent all
the characters in the world with just 16 bits. So Unicode was extended to use
21 bits. Now over one million characters can be encoded (1,114,111 to be exact).

The size of `char` couldn't be changed from 16 bits to 21 bits. This would've
caused a disaster in the software industry.

You can use the characters outside U+FFFF with *supplementary characters*.

## Using Unicode in Java

A supplementary character is any character within the range U+10000 and U+10FFFF.
You need to use a pair of `char` values to represent them. The pair of codepoints
which represent a supplementary character are known as surrogates.

The first codepoint is known as the high surrogate. It is in the range of U+D800
to U+DBFF.

The second codepoint is known as the low surrogate. It is in the range of U+DC00
to U+DFFF.

For example, the **DESERET CAPITAL LETTER LONG I** (U+10400), is represented with
U+D801 and U+DC00 surrogate pair.
```
char highSurrogate = '\uD801';
char lowSurrogate = '\uDC00';
```