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

