# Tyler's Programming Principles
My own version of Uncle Bob's SOLID

1. **Single Inheritance Principle: A subclass must never inherit from more than one class.**
  * Keep inheritance chains short, ideally no longer than two levels. This approach boosts code readability and simplifies tracking where methods come from. Consider this: You're troubleshooting a `d_object.cancel()` issue. `d_object` comes from class D, which inherits from C, then B, and finally A. If class D lacks a `cancel()` method, you must backtrack through C to B, where `cancel()` is defined, using a function from A. This convoluted path can be overwhelming. Simplify by having classes inherit directly from the closest relevant class, reducing the need to navigate through multiple layers to understand functionality. While this might introduce some code repetition, it significantly aids in understanding and maintaining the code.
2. **Descriptive Naming Principle: Write really descriptive variable and function names.**
  * Someone who does not code should be able to read your program's function and class names and get a decent understanding of what is going on.
  * Write your code as if it is going to be read by novice programmers.
  * DO NOT name any of your functions "go", "task", "register", or the absolute worst, "_".
  * Acceptable function names: go_to_top_of_webpage, start_data_transformation_task, register_new_user
