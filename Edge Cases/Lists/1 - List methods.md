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

| Method              | Behavior                                                 | Example Result                                                           |
| ------------------- | -------------------------------------------------------- | ------------------------------------------------------------------------ |
| `.append(obj)`      | Adds the object as a **single entry** at the end.        | `[1].append([2, 3])` $`\rightarrow`$ `[1, [2, 3]]`                       |
| `.insert(i, obj)`   | Places the object as a **single entry** at index `i`.    | `[1].insert(0, print)` $`\rightarrow`$ `[<built-in function print>, 1]`  |
| `.extend(iterable)` | Unpacks an **iterable** and adds each item individually. | `[1].extend([2, 3])` $`\rightarrow`$ `[1, 2, 3]`                         |
<hr>

**A Weird Example**

You can create a list that looks like a fever dream of data types:

```python
import math

def my_func():
    return "Hello"

mixed_list = []
mixed_list.append(42)              # Integer
mixed_list.append("Python")        # String
mixed_list.append(my_func)         # A function object
mixed_list.append(math)            # A module
mixed_list.append(mixed_list)      # The list itself (Recursive!)

print(mixed_list)
```
