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
