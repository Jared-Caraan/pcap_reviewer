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

   | Method | Purpose |
   | ------ | ------- |
   | `__bool__(self)` | Defines the explicit boolean value.                           |
   | `__len__(self)`  | If `__bool__` is missing, Python checks if length is $`> 0`$. |

   **Example of Custom Logic:**
   
   If you have a `Bank` class, you might want it to evaluate to `False` if it has no money, regardless of whether the object exists.

   ```python
   class Bank:
        def __init__(self, balance):
            self.balance = balance
   
        def __bool__(self):
            return self.balance > 0
   
    vault = Bank(0)
    if not vault:
        print("The bank is broke!") # This prints because balance is 0
   ```

   If the `__bool__` method is missing from your class, Python doesn't just give up. It follows a specific fallback hierarchy to determine if the instance is "Truthy" or "Falsy."
   
   Here is exactly what happens when you evaluate `if vault:`:

   1. **The Fallback Hierarchy**
      Python checks for methods in this specific order:
      
      1. Check `__bool__`: If it exists, use its return value (`True` or `False`).
      2. Check `__len__`: If `__bool__` is missing, Python calls `len(instance)`.
         - If `__len__` returns a value greater than 0, the object is `True`.
         - If `__len__` returns 0, the object is `False`.
      3. Default to `True`: If **neither** method is defined, the object is considered **True** by default.

   2. **Scenario: No `__bool__` and No `__len__`**

      In this case, every instance you create will be `True`, even if it's "empty" or has a balance of 0.

      ```python
      class Bank:
          def __init__(self, balance):
              self.balance = balance
      
      vault = Bank(0)
      
      if vault:
          print("This will ALWAYS print.") 
      # Result: The object exists in memory, so it is Truthy.
      ```

   3. **Scenario: No __bool__ but __len__ exists**

      If you define `__len__`, Python uses it as a proxy for truthiness. This is why empty lists `[]` are `False`—they have a length of 0.

      ```python
      class Bank:
          def __init__(self, accounts):
              self.accounts = accounts # Assume this is a list
      
          def __len__(self):
              return len(self.accounts)
      
      vault = Bank([]) # Empty list of accounts
      
      if not vault:
          print("The bank has no accounts.") 
      # Result: This prints! Python saw no __bool__, checked __len__, got 0, and treated it as False.
      ```

   **Summary Table: How Python Decides**

   | Does `__bool__` exist? | Does `__len__` exist? | Result of `bool(obj)`             |
   | ---------------------- | --------------------- | --------------------------------- |
   | **Yes**                | Irrelevant            | Returns `__bool__()`              |
   | **No**                 | **Yes**               | `True` if `len > 0`, else `False` |
   | **No**                 | **No**                | Always `True`                     |

Why does it default to **`True`**?

In Python’s philosophy, an object is a "thing." Unless the object specifically defines itself as being empty or null (via length or a boolean flag), the mere fact that it exists in your computer's memory makes it "True."
