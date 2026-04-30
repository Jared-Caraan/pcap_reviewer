## Shallow/Deep Copy

When you "copy" by referencing variables, you aren't actually creating a copy of the data; you are creating a new reference to the same object in memory.

### The "Alias" Trap (Shallow Copy via Assignment)

The most common edge case occurs when people think `b = a` creates a copy. In reality, both variables point to the exact same memory address.

```python
# The Setup
list_a = [1, 2, [3, 4]]
list_b = list_a  # This is just an alias

# The Edge Case: Mutating the "copy"
list_b[0] = 99

print(f"Original: {list_a}") # Output: [99, 2, [3, 4]]
print(f"Alias:    {list_b}") # Output: [99, 2, [3, 4]]
print(list_a is list_b)      # Output: True (Same ID)
```
<hr>

### Shallow Copy via Slicing (The "One-Level" Edge Case)

Using the slice operator `[:]` creates a new top-level object, but it **does not** copy the nested objects. It only copies the references to them.

**The Edge Case:** Modifying a nested mutable object affects both lists, but modifying a top-level immutable object does not.

```python
original = [[1, 2], 3]
shallow  = original[:] # New list object, same internal references

# Scenario A: Changing a top-level integer (Safe)
shallow[1] = 100 

# Scenario B: Changing a nested list (The Trap)
shallow[0][0] = "X"

print(f"Original: {original}") # Output: [['X', 2], 3]
print(f"Shallow:  {shallow}")  # Output: [['X', 2], 100]
```
<hr>

### Deep Copy via List Comprehension (The Nesting Limit)

Since we aren't using the `copy` module, a common "hack" for a deep copy is using list comprehension. However, the edge case here is **depth**. This only works for one level of nesting.

```python
# A "Pseudo-Deep" Copy
data = [[1, 2], [3, 4]]
pseudo_deep = [item[:] for item in data]

pseudo_deep[0][0] = 99

print(f"Original: {data}")        # Output: [[1, 2], [3, 4]] (Safe!)
print(f"Pseudo:   {pseudo_deep}") # Output: [[99, 2], [3, 4]]
```

**The Critical Edge Case:** If you have a 3rd level of nesting (e.g., `[[[1]]]`), the list comprehension above fails to be "deep" because it only goes one level down. To truly deep copy without the module, you would need a recursive function.
<hr>

### Summary Table: Reference Behavior

| Method                  | Top-level ID | Nested Object ID | Risk                                 |
| ----------------------- | ------------ | ---------------- | ------------------------------------ |
| `b = a`                 | **Shared**   | **Shared**       | Any change affects both.             |
| `b = a[:]`              | **Unique**   | **Shared**       | Changing nested lists affects both.  |
| `b = [i[:] for i in a]` | **Unique**   | **Unique**       | Fails if nesting is > 2 levels deep. |
<hr>

### The copy() Method (Built-in Shallow Copy)

Most built-in collections (list, dict, set) have a `.copy()` method. This is functionally identical to the slicing `[:]` trick but is more readable.

**The Edge Case: Shared References in Dictionaries**
If a dictionary contains a list, the `.copy()` method creates a new dictionary, but the list inside remains the same instance in memory.

```python
original_dict = {"scores": [10, 20], "user": "Alex"}
shallow_dict = original_dict.copy()

# Edge Case: Modifying the nested list
shallow_dict["scores"].append(30)

print(original_dict["scores"]) # Output: [10, 20, 30] (Modified!)
print(shallow_dict is original_dict) # Output: False
```
<hr>

### The `copy` Module: `copy.deepcopy()`

The `deepcopy()` function is the "nuclear option." It recursively clones every object it finds.

**The Edge Case: Self-Referential (Recursive) Objects**
What happens if a list contains itself? A naive recursive copy would enter an infinite loop. `deepcopy` handles this by keeping a memo (a dictionary) of objects it has already copied.

```python
import copy

list_a = [1, 2]
list_a.append(list_a) # list_a is now [1, 2, [...]]

# Edge Case: Deepcopying a recursive structure
list_b = copy.deepcopy(list_a)

print(len(list_b))      # Output: 3
print(list_b[2] is list_b) # Output: True (It correctly recreated the self-reference)
```
<hr>

### The `list()` Constructor

Using the constructor `new_list = list(old_list)` is another common way to copy.

**The Edge Case: Non-List Iterables**
The constructor doesn't just copy; it **evaluates**. If you pass it a generator, it "exhausts" the generator to create the list. You cannot "copy" a generator this way to use it twice.

```python
gen = (x for x in range(3))
list_1 = list(gen)
list_2 = list(gen) # The generator is already empty!

print(list_1) # Output: [0, 1, 2]
print(list_2) # Output: []
```
<hr>

### Compound Edge Case: Objects with Custom `__copy__`

When working with Classes, you can actually break the standard behavior of the `copy` module by defining your own logic.

```python
import copy

class Stubborn:
    def __init__(self, value):
        self.value = value
    
    def __copy__(self):
        # Edge Case: Force the copy to always have a specific value
        return Stubborn("I refuse to be a normal copy")

a = Stubborn("Original")
b = copy.copy(a)

print(b.value) # Output: "I refuse to be a normal copy"
```
<hr>

### Comparison of Methods

| Method            | Type     | Depth        | Best Use Case                              |
| ----------------- | -------- | ------------ | ------------------------------------------ |
| `obj.copy()`      | Shallow  | 1 Level      | Quick copies of simple dicts/lists.        |
| `list(iterable)`  | Shallow  | 1 Level      | Converting types while copying.            |
| `copy.copy()`     | Shallow  | 1 Level      | Generic shallow copy for any object type.  |
| `copy.deepcopy()` | **Deep** | **Infinite** | Complex, nested data or recursive objects. |

> [!NOTE]
> In Python, small integers (usually -5 to 256) and short strings are "interned." Even if you try to make a unique copy of the number `10`, Python will often point both variables to the same memory address anyway to save space. This is a harmless edge case because those types are immutable!
