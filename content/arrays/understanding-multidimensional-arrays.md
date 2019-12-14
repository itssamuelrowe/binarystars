In Java all arrays are objects, which means you can store an array inside another
array. Such an arrangment of arrays allows you to create multidimensional
arrays.

The two dimensional array is very common compared to other higher dimensional
arrays. A common use of a two dimensional array is to represent data in grids,
such as cartesian planes and matrices. 

In an array variable declaration statement, the number of square bracket pairs you
write determines the dimensions of your array. For example, if you write two
pairs of square brackets, you are creating a two dimensional array. Similarly,
if you write three pairs of square brackets, you are creating a three dimensional
array.

Here is an example of a two dimensional array.
```
int matrix[][] = new int[5][10];
```

This example allocates an array with 5 slots in the first dimension. After which,
5 arrays of size 10 are created and assigned in each of those slots. Which means,
there are 50 slots in the array, organized in two dimensions.

Here is an example program, which prints the layout of the two dimensional
array.

```
public class TwoDimensionalArrayDemo {
    public static void main(String ... arguments) {
        int array[][] = new int[5][10];
        
        int k = 0;
        for(int i = 0; i < array.length; i++) {
            for(int j = 0; j < array[i].length; j++) {
                array[i][j] = k++;
            }
        }
        
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                System.out.print(array[i][j] + "\t");
            }
            System.out.println();
        }
    }
}
```

This example produces the following output.
```
0       1       2       3       4       5       6       7       8       9
10      11      12      13      14      15      16      17      18      19
20      21      22      23      24      25      26      27      28      29
30      31      32      33      34      35      36      37      38      39
40      41      42      43      44      45      46      47      48      49
```

Java allows you allocate memory for the first `n` dimensions. You can allocate
other dimensions later.

Here is an example which demonstrates this technique.
```
int array[][] = new int[3][];
array[0] = new int[4];
array[1] = new int[8];
array[2] = new int[2];
```

In this example, you  allocates memory for the first dimension of the array.
Then you manually allocate the second dimension. The main advantage of this
technique is that it allows you to create different sized arrays in a given
dimension, as shown here.

Here is a modified version of the earlier program which prints the layout
of an unevenly distributed multidimensional array.

```
public class UnevenTwoDimensionalArrayDemo {
    public static void main(String ... arguments) {
        int array[][] = new int[3][];
        array[0] = new int[4];
        array[1] = new int[8];
        array[2] = new int[2];
        
        int k = 0;
        for(int i = 0; i < array.length; i++) {
            for(int j = 0; j < array[i].length; j++) {
                array[i][j] = k++;
            }
        }
        
        for (int i = 0; i < array.length; i++) {
            for (int j = 0; j < array[i].length; j++) {
                System.out.print(array[i][j] + "\t");
            }
            System.out.println();
        }
    }
}
```

The output of this program is shown here.

```
0       1       2       3
4       5       6       7       8       9       10      11
12      13
```

Unevenly distributed multidimensional arrays are not very common. This is usually
not how multidimensional arrays are designed. However, irregular arrays are useful
in some case.