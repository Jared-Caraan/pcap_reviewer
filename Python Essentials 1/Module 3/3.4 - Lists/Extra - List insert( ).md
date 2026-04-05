### List - insert( )

Python’s `insert()` method is very "forgiving" when it comes to index ranges. It doesn't throw an `IndexError`, even if you provide a number that seems way out of bounds.

**How it Behaves**

When you call `list.insert(index, element)`:

- **If the index is greater than the current length:** Python simply appends the element to the very end of the list. It treats any value $\ge \text{len(list)}$ as "put this at the end."
- **If the index is a large negative number:** It does the opposite—it will prepends the element to the very beginning (index 0).
<hr>

**See it in Action**

Here is a quick breakdown of what happens under the hood:

| Scenario           | Code Example              | Resulting List |
| ------------------ | ------------------------- | -------------- |
| **Normal Insert**  | `[1, 2].insert(1, 'A')`   | `[1, 'A', 2]`  |
| **Index > Length** | `[1, 2].insert(100, 'B')` | `[1, 2, 'B']`  |
| **Large Negative** | `[1, 2].insert(-99, 'C')` | `['C', 1, 2]`  |

**Why does it do this?**

Python is designed to be "batteries included" and user-friendly. Instead of crashing your program because a calculation resulted in an index of 6 on a list of 5 items, it assumes your intent was just to place the item as far in that direction as possible.

However, if you specifically need an item to be at the end, using `.append()` is usually preferred because it's more readable and slightly faster.
