## Diamond problem

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-diamond-problem_.

### Definition

We've already explained some of the problems arising from multiple inheritance. There's one more issue that we may encounter, and we're going to talk about it in this video. The problem is called the **diamond problem**. Suppose that you have a top superclass `A` and two subclasses that inherit from it `B` and `C`. There's also a bottom row subclass named `D` which inherits from both `B` and `C`.

<img width="190" height="187" alt="image" src="https://github.com/user-attachments/assets/7048e21e-7bc1-4925-954b-609192acd7c6" /><br>

### Example

<img width="602" height="412" alt="image" src="https://github.com/user-attachments/assets/a664228d-d39d-48d8-a83a-054214b4c400" /><br>

<img width="767" height="338" alt="image" src="https://github.com/user-attachments/assets/cd7d6552-fab0-4ccc-bcab-b4fbb6064a8d" /><br>

This set up is what we call the diamond problem. It's a situation in which due to the class hierarchy, it is not clear which method version should be inherited. There is more than one candidate and the choice is ambiguous. You know that Python first looks for a method within the object itself, and when it can't find one, it scans the super classes from left to right. This means that the choice of the method depends on how you define the inheritance.

<img width="546" height="132" alt="image" src="https://github.com/user-attachments/assets/96c3cfba-73dd-455c-bcd8-c1fb92f12ebc" /><br>

As you can see, the answer to the diamond problem in Python is quite simple. You just need to remember the method resolution order.
