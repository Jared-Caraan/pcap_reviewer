### List Methods Parameters

Python lists are **heterogeneous containers**, meaning they are perfectly happy to hold a chaotic mix of whatever you throw at them.

In Python, "everything is an object," and list methods like `append()`, `insert()`, and `extend()` treat all objects with the same level of indifference.

**What can you put in a list?**

The short answer: **Anything.** Here are some examples of "unconventional" items that Python lists accept without hesitation:

- **Other Lists (Nesting):** You can put a list inside a list to create matrices or trees.
- **Functions and Classes:** You can store the actual function object, not just its result.
- **Modules:** You can literally append the `math` or `os` module to a list.
- **Custom Class Instances:** Any object you’ve defined yourself.
- **The list itself:** You can actually append a list to itself, creating a circular reference.
<hr>

**Comparison of Methods**

While they all accept any object, they handle them differently:
