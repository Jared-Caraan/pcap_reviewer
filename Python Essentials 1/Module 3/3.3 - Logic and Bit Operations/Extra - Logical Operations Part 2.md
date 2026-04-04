### Logical Operations Part 2

1. **The Core Rule: Truthiness**

   Every object in Python is considered True unless its class defines a `__bool__()` method that returns `False` or a `__len__()` method that returns `0`.

   **Common "Falsy" Values:**
   - **Constants:** `None` and `False`.
   - **Numeric Zero:** `0`, `0.0`, `0j`.
   - **Empty Sequences/Collections:** `''` (empty string), `[]` (list), `()` (tuple), `{}` (dict), `set()`.

2. **Functions and Classes**

   Both functions and class objects are almost **always True**. This is because they are considered "existing objects" in memory.

   - **Functions:** Even if a function returns `None` or `False`, the function **object itself** is True.
   - **Classes:** A class definition is an object. `bool(MyClass)` will always be `True`.
   <br>
   
   ```python
   def my_function():
       return False
  
   if my_function:  # This is TRUE because the function exists
       print("The function object is truthy!")

   if my_function(): # This is FALSE because we called it and it returned False
       print("This won't print.")
   ```

3. **Data Structures (Lists, Dicts, Sets)**

   For data structures, truthiness is tied to **size**.

   - **Empty** = `False`
   - **Non-empty** (even with one element) = `True`
  
   This allows for the "Pythonic" way of checking if a list has items:

   ```python
   items = []

   if not items:
       print("The list is empty!")
   ```

4. **Custom Objects (Class Instances)**

   When you create an instance of a class, you can control its truth value by overriding magic methods.

   
