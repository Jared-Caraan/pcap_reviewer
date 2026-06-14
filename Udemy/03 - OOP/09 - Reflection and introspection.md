## Reflection and introspection

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-reflection-introspection_.

### Definition

In many objective languages, there are two special kinds of operations - **introspection** and **reflection**.

Introspection is the ability of a program to check the type of an object or the properties of an object at runtime. In other words, introspection allows you to get some information about a given object during the program execution.

Reflection is similar, but goes one step further. It allows you to change the properties and methods of a given object during the program's execution. Python allows you to do both introspection and reflection, and you actually already know most of the tools that you need.

We will see that based on an example.

Suppose that you write a Python module that you believe will be useful for other programmers. You want to create a function that accepts an object of any type of class, goes through all the properties of the object, and for each string property, it changes the property to an empty string. We'll call this function `empty_string()` because we want it to change all the strings into empty ones.

Normally such a function is impossible. You don't know what kind of classes your users will have. You don't know what kind of properties these classes will have as well. So how can you write such a function?
The answer is introspection and reflection. Introspection will help you to get to know all the properties that are available for a given object of any type of class. Reflection, in turn will allow you to change all these properties that you need. Let's see how this can be achieved in practice.
<hr>

### Implementation

<img width="717" height="148" alt="image" src="https://github.com/user-attachments/assets/5918270a-6067-4907-9039-d3a29274b559" /><br>

We get an object as a parameter, but we know next to nothing about it. We don't know which class was used to create it. However, we know that the built-in `__dict__` property is a dictionary that contains all the properties of the object, no matter what kind of object it is. Because it is a dictionary, we can actually use the `keys()` method. This for loop will inspect all the properties of the given object one by one. So for each property name we use another function worth knowing - `getattr()`. It takes two arguments - an object and a name of its property and it returns the value of the given property.

Next is `isinstance()`. `isinstance()` takes two arguments - the first one is a variable, the second one is a type. `isinstance()` checks if the variable is of the given type, we put `str` here because we want to check for strings, but you could also put something like `int` for integers or maybe you could put a custom class name as well. If the value of the given property is indeed a string, we used the third new function `setattr()`.

This function sets a new value for a given property in a given object. It takes three arguments - the object, the name of the property and the new value. Here we just set the new value to an empty string.

<img width="766" height="713" alt="image" src="https://github.com/user-attachments/assets/14cd5e17-4d3e-4038-8f6c-4602571bbca1" /><br>

You can see that the function works correctly. `Alex` now has an empty first name, so the function correctly identified that there is a first name and last name property. And because both of them are strings, they were both set to empty ones. And this is why the introduced method now returns an empty name.
