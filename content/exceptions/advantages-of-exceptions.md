The advantages of exceptions are as follows.

 * You can separate error handling from your algorithm.

  With exceptions you can separate the details of what happens when an unexpected
  situation occurs. You can separate such logic from the main logic of your program.
  
  In other programming languages, error detection, reporting, and handling often
  lead to complex and confusing code.

  Exceptions allow you to keep your source code clean and organized.
  
 * Your methods don't have to forward errors.
 
    Exceptions have the ability to propagate up the stack of methods currently
    invoked. For example, assume that a method is the fourth method in a series
    of nested method calls. If the first method is the only method interested in
    handling the error, and the error occurs in the fourth method, you don't
    have to manually forward the error. Throwing an exception does the job
    for you. This allows you to generalize error handling in one common place.
 
 * You can group and differentiate error conditions. 
    
    Because exceptions are objects, you can group or categorize them using their
    class hierarchy. An example of a group of related exception classes are the exception
    classes which inherit the `java.io.IOException` class. The IOException class
    represents an input/output error. Its descendants represent more specific errors.
    For example, `FileNotFoundException` indicates that a file could not be found
    on the disk.


All these advantages make exceptions reliable, stable, and secure.