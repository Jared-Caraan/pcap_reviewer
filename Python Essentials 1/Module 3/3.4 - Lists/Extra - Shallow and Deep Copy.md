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

> [!NOTE]
> In Python, small integers (usually -5 to 256) and short strings are "interned." Even if you try to make a unique copy of the number `10`, Python will often point both variables to the same memory address anyway to save space. This is a harmless edge case because those types are immutable!
