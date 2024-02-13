# Tyler's Programming Principles
My own version of Uncle Bob's SOLID

1. **Single Inheritance Principle: A subclass must never inherit from more than one class.**
  * Let's say you have a parent class, class A.  You have a child class, class B, which inherits from Class A.  Then you have class C, which inherits from Class B.  Finally, you have class D, which inherits from class C.  Your manager tells you to fix a particular line of code that isn't working.  The line of code is:
    ```d_object.cancel()```
    You discover that d_object is an object instantiated from class D.  However, in D's definition, there is no cancel() method.  You now have to look at class C.  Class C also has no cancel method, so now you have to look at class B.  Class B has a cancel method, but it takes as an argument another function, which is defined in Class A.  By the time you have figured out what d_object.cancel() does, you have forgotten your name, your address, and even your marital status.  This tragic incident could have been avoided if we limited the number of classes a subclass can inherit from.  For example, class B would inherit from class A. Class C would also inherit from Class A, or from a new class if necessary.  This way, if you want to find out what .cancel() does, you only have to go up one level, and you have a much stronger chance of remembering your marital status by the time you are done.  This technique reduces cognitive load on the reader.  Yes, this may lead to some code duplication:  I know the adage DRY, don't repeat yourself.  However, readability is king, and in this instance I feel it is more important to write code that is easily readable.
2. **Descriptive Naming Principle: Write really descriptive variable and function names.**
     * Someone who does not code should be able to read your program's function and class names and get a decent understanding of what is going on.
     * DO NOT name any of your functions "go", "task", "register", or the absolute worst, "_".
     * Acceptable function names: go_to_top_of_webpage, start_data_transformation_task, register_new_user
