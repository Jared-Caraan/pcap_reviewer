## Exceptions as objects

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exceptions-objects_.

We are going to talk about the objective nature of exceptions. Yes, exceptions in Python are objects. Whenever an exception is raised in Python, an object of the given exception class is created and it goes through all the branches of the try except block to find a matching branch. The exception object has some information that you can use to precisely identify what went wrong. In order to get that information, you need to extend your `except` block using a special keyword `as`.

### Sample Usage

<img width="712" height="357" alt="image" src="https://github.com/user-attachments/assets/77d8a1b2-722c-4cf9-a7e6-97cb59398898" /><br>

We can refer to the exception object within the `except` block using the identifier `e`. You can see that when we try to print the exception object, we get some detailed info about what the problem was. That's because by default, the exception class implements a version of the `__str__` method common to all objects.
<hr>

### Exception Hierarchy

<img width="638" height="232" alt="image" src="https://github.com/user-attachments/assets/ce4a4e55-187a-4797-99b9-6f71d454afc6" /><br>

You can see all the subclasses that directly inherit from the `BaseException` class and if you try one of the subclasses like `Exception`:

<img width="628" height="542" alt="image" src="https://github.com/user-attachments/assets/bb1c55de-7b4d-40c9-a9ba-86c00bc56e7d" /><br>

There are a lot of classes that directly inherit from `Exception`. Each exception class that inherits from `BaseException` has a property named `args`. It's a tuple which contains all the arguments passed to the constructor.
<hr>

### `args`

<img width="392" height="165" alt="image" src="https://github.com/user-attachments/assets/960d8909-b531-48ce-b04e-3d3b03492d7d" /><br>

In this simple case, the code only raises a general `Exception` when we try to print the property of the `Exception` object. You can see that it's actually empty. This means that no argument was passed to the class constructor.

<img width="572" height="173" alt="image" src="https://github.com/user-attachments/assets/58ec3a41-4d55-42b4-947b-96f598462fe5" /><br>

After the keyword `raise` and the `Exception` class, we provided a pair of parenthesis and we put a string inside. We're actually invoking the constructor of the `Exception` class with one argument. `Exception` classes in Python are constructed in such a way that you can pass even more arguments to the `Exception` constructor.

<img width="947" height="158" alt="image" src="https://github.com/user-attachments/assets/b5d28157-0674-47a9-bf17-4f1bd5aeb202" /><br>

All of the arguments passed to the constructor are added to the property. This feature is typically used to pass some details about why a given exception is raised. In fact, you can easily see that Python adds some arguments when it raises exceptions automatically for you.

<img width="387" height="157" alt="image" src="https://github.com/user-attachments/assets/f44d4c7f-f371-423e-b490-2acb571af891" /><br>
<img width="655" height="146" alt="image" src="https://github.com/user-attachments/assets/99fa2df3-289c-4e2c-9867-797efbc1b135" /><br>

And as you can see, Python added a short explanation to the `args` tuple.
