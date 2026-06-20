## Exception hierarchy

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exception-hierarchy_.

### Hierarchy Diagram

Now let's talk about exception hierarchy in Python. Python has over 60 built in exception types. Naturally, you don't need to memorize them all as a beginner, but it's good to have a general understanding of their hierarchy.

<img width="1350" height="592" alt="image" src="https://github.com/user-attachments/assets/b4046cf5-ed30-41c4-8e9f-a20a5169be51" /><br>

At the top of the hierarchy there is `BaseException`. This exception is used internally by Python. You will probably never see `BaseException` raise in your own programs. This `BaseException` serves more as a template for other more specific exception types. Such templates that are not very specific-concrete exceptions are typically called **abstract** or **abstractive** exceptions.

One level down in the hierarchy, you can see three exceptions - `Exception`, which has lots of other exceptions underneath and two others, `SystemExit` and `KeyboardInterrupt`. 

#### SystemExit

`SystemExit` is an exception raised when we call a special method - `sys.exit`. This method is used to terminate or in other words, close your program. Up until now, your programs closed on their own when they reached and executed the last line of code. `sys.exit` allows you to close your program manually, it is not used very often, but may sometimes come in handy in very specific situations.

<details>
<summary>SystemExit</summary>

<br>
<img width="1437" height="522" alt="image" src="https://github.com/user-attachments/assets/c977909a-3e8c-4337-ba61-efd91bb0003b" /><br>

</details>

#### KeyboardInterrupt

Now, let's talk about `KeyboardInterrupt`. This simple exception is raised when the user presses a key combination that causes an interrupt to the executing script.

<details>
<summary>KeyboardInterrupt</summary>

<br>

While the script's running, stopping the kernel produces a `KeyboardInterrupt`.
<img width="1236" height="522" alt="image" src="https://github.com/user-attachments/assets/163b4b14-fc91-4325-bf1f-27da240fe9db" /><br>

</details>

#### Exception

`Exception` is a bit similar to `BaseException`. Both of them often serve as templates for other exceptions. The difference is that `BaseException` is typically only used as a template for internal python exceptions, while `Exception` can also be used as a template for your own exceptions. `Exception` is also a template for many built in Python exceptions. In fact, most of the exceptions that you've seen so far -`ValueError`, `ZeroDivisionError` and so on. All of these can be found under exception in the hierarchy.

#### ArithmeticError

This is the base class for a variety of mathematical arithmetic errors, and this category you can see `ZeroDivisionError`. We've already seen this exception when we try to divide by numbers zero.

#### LookupError

It has two children underneath - `IndexError` and `KeyError`. These two exceptions will appear when you work with collections such as lists or dictionaries.

<details>
<summary>IndexError</summary>

<br>
<img width="880" height="268" alt="image" src="https://github.com/user-attachments/assets/2104cd2c-6381-488a-935f-1eba5cfa92b1" /><br>

</details>

<details>
<summary>KeyError</summary>

<br>
<img width="872" height="280" alt="image" src="https://github.com/user-attachments/assets/35af4b78-6138-4500-8914-21d6d308dfbf" /><br>

</details>

#### TypeError

When working with user input, `TypeError` indicates that the type of data you're trying to use is not correct.

</details>

<details>
<summary>TypeError</summary>

<br>
<img width="877" height="282" alt="image" src="https://github.com/user-attachments/assets/90110d76-b6ff-4095-a35e-bfddf8e4d615" /><br>

</details>

#### ValueError

This exception is raised when a functional method to receives an argument of the correct type, but with an actual value that is invalid for some reason.

<details>
<summary>ValueError</summary>

<br>
<img width="877" height="251" alt="image" src="https://github.com/user-attachments/assets/8da67d26-dfd0-4f82-b1ea-d3df7aaccf05" /><br>

</details>

One thing to keep in mind is that Python typically erases the most specific exception it can. This means that when `ZeroDivisionError`, a type of `ArithmeticError` and you try to divide by zero in your program, you will see `ZeroDivisionError` thrown and not `ArithmeticError`. That's because `ZeroDivisionError` is more specific than `ArithmeticError` or in other words, it is placed lower in the exception hierarchy.
