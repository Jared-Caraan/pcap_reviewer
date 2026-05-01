### List - extend( )

When you pass a dictionary to `.extend()`, Python iterates over it. By default, iterating over a dictionary only yields its keys, not its values or the key-value pairs.

**How it Works**

The `.extend()` method expects an iterable (like a list, tuple, string, or dictionary). It loops through that **iterable** and appends each element to the end of the list.

```python
my_list = [1, 2, 3]
my_dict = {"a": 100, "b": 200, "c": 300}

my_list.extend(my_dict)

print(my_list)
# Output: [1, 2, 3, 'a', 'b', 'c']
```
<hr>

**Controlling What Gets Added**

If you want something other than the keys, you have to specify which "view" of the dictionary you want to extend with:

| Goal                    | Method to use                      | Resulting List                   |
| ----------------------- | ---------------------------------- | -------------------------------- |
| **Add Keys (Default)**  | `my_list.extend(my_dict)`          | `[..., 'a', 'b', 'c']`           |
| **Add Values**          | `my_list.extend(my_dict.values())` | `[..., 100, 200, 300]`           |
| **Add Key-Value Pairs** | `my_list.extend(my_dict.items())`  | `[..., ('a', 100), ('b', 200)]`  |

**Important Details**

- **Order:** As of Python 3.7+, dictionaries maintain insertion order. So, `.extend()` will add the keys/values in the same order they were added to the dictionary.
- **Unpacking Tuples:** When you use `.extend(my_dict.items())`, the key-value pairs are added as tuples. The list becomes a "list of tuples," it doesn't flatten them into individual elements.
  - If you want a flat list like `['a', 100, 'b', 200]`, you would need a list comprehension or a loop; `.extend()` won't do that automatically.
<hr>

**Common Mistake: `.append()` vs `.extend()`**

It’s easy to mix these up when dealing with dictionaries:

- `my_list.append(my_dict):` Adds the **entire dictionary object** as a single element at the end.
- `my_list.extend(my_dict):` Breaks the dictionary apart and adds its keys as **separate elements**.
