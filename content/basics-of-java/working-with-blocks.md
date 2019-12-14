A block is a group of zero or more statements within braces.

A block begins with an opening brace `{` and ends with a closing brace `}`.

You can write any number of statements, including block statements, within the
braces.

For example, this is an *empty block*.
```
{
}
```

For example, this is a block with four statements.
```
{
    int i;
    int j;
    i = 10;
    j = 20;
}
```

A block is a type of statement. Thus, you can use a block to execute more
than one statements whenever a construct needs a statement. You will learn
more about this when you learn about compound statements.

Here's an example of block statements.

```
public class Blocks {

    public static void main(String... arguments) {
        {
            System.out.println("This is the outer block.");
            {
                System.out.println("This is the inner block.");
            }
        }
    }
}
```