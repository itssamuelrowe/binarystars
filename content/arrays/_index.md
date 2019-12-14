So far in this course, you have written programs which work with few variables.
For example, consider a program which stores the details of a student and prints
it out. You would create a class to represent the student. Each instance of this
class stores the details of a student, therefore, you would create a variable which
references a student object. What if there were four students? You would create
four variables which reference four student objects. What if there were a hundred
students, or even thousand? In such cases creating hundreds of variables is
absurd.

A better solution would be to use a list which keeps track of the students.
Java provides a fundamental type known as an array which is similar to lists.
In this chapter you will learn about arrays, their declaration and initialization.
Finally, we will learn a variation of arrays known as multdimensional arrays.

Interestingly, Java actually includes classes which implement the full fledged
behavior of lists. However, these lists are not fundamental objects like arrays,
that is, they are not treated specially by Java. Further, some of these lists
internally store the values using arrays.