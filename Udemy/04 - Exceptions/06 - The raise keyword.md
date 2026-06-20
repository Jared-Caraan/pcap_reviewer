## The raise keyword

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exceptions-raise_.

So far we've only seen examples where Python raises exceptions for us. When we try to divide by zero, Python automatically raise an exception; when we tried to access a non-existing array index, Python raise an exception. All of that happened automatically for us.

Python allows you to raise exceptions on your own. Raising exceptions on your own is typically used in two types of situations:
1. When you write tests to check your programs, you can raise exceptions to verify how your piece of code will behave, if during the execution of your program, Python suddenly raises a real exception.
2. The second use case is when you want to make another part of the program responsible for handling the exception. This can be very useful in larger applications.

To raise an exception, we use the keyword to `raise`, followed by the name of the exception.

### Sample Implementation

<img width="952" height="685" alt="image" src="https://github.com/user-attachments/assets/0335ac1c-0f2e-4e0e-b2bc-50a08ce79f30" /><br>

So here in the `return_bigger` function, we assume that both arguments will be of type integer. We checked out at the very beginning of the function, if at least one of the numbers is not an integer, we manually raise a `ValueError` here by using the `raise` keyword.

There's also another usage of the word `raise`. You can use it without any exception name inside the except branch. This instruction will then reraise the very same exception as currently handled.

<details>
<summary>Version without raise</summary>

<br>
<img width="558" height="251" alt="image" src="https://github.com/user-attachments/assets/db20fd21-e112-4ed1-805d-e4366627fa5b" /><br>

</details>

<details>
<summary>Version with raise</summary>

<br>
<img width="912" height="600" alt="image" src="https://github.com/user-attachments/assets/ce82b356-75ea-4804-8ae7-a44351239c72" /><br>

</details>

This programming technique is sometimes used when you only want to handle an exception partially, and then you want to raise the exception again.
