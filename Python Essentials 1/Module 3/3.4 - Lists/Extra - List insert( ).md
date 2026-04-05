### List - insert( )

Python’s `insert()` method is very "forgiving" when it comes to index ranges. It doesn't throw an `IndexError`, even if you provide a number that seems way out of bounds.

**How it Behaves**

When you call `list.insert(index, element)`:

- **If the index is greater than the current length:** Python simply appends the element to the very end of the list. It treats any value $\ge \text{len(list)}$ as "put this at the end."
- **If the index is a large negative number:** It does the opposite—it will prepends the element to the very beginning (index 0).
<hr>

**See it in Action**

Here is a quick breakdown of what happens under the hood:

