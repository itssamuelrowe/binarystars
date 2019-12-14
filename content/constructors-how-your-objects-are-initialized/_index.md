When you create an object using the `new` operator, Java does several things
for you.

Here is the gist of what happens when you create an object.
    * First, the memory to store the object is allocated.
    * The allocated memory buffer is initialized internally to create the
      object.
    * The object is associated with the class from which it was created.
    * The virtual method tables are generated.
    * Finally, a special method defined in the objects class is invoked.
      This method is called a constructor.

In this chapter, we will learn about constructors. We will see how to work with
constructors, including their declaration and invocation.