### Key takeaways

1. There are two types of loops in Python: `while` and `for`:

   - the `while` loop executes a statement or a set of statements as long as a specified boolean condition is true, e.g.:

     ```python
     # Example 1
      while True:
          print("Stuck in an infinite loop.")

     # Example 2
      counter = 5
      while counter > 2:
          print(counter)
          counter -= 1
     ```

   - the `for` loop executes a set of statements many times; it's used to iterate over a sequence (e.g., a list, a dictionary, a tuple, or a set - you will learn about them soon) or other objects that are iterable (e.g., strings). You can use the `for` loop to iterate over a sequence of numbers using the built-in `range` function. Look at the examples below:

     ```python
     # Example 1
      word = "Python"
      for letter in word:
          print(letter, end="*")

     # Example 2
      for i in range(1, 10):
          if i % 2 == 0:
              print(i)
     ```

2. You can use the `break` and `continue` statements to change the flow of a loop:

   - You use `break` to exit a loop, e.g.:

     ```python
     text = "OpenEDG Python Institute"
     for letter in text:
         if letter == "P":
             break
         print(letter, end="")
     ```
     
   - You use `continue` to skip the current iteration, and continue with the next iteration, e.g.:

     ```python
     text = "pyxpyxpyx"
     for letter in text:
         if letter == "x":
             continue
         print(letter, end="")
     ```

3. The `while` and `for` loops can also have an `else` clause in Python. The `else` clause executes after the loop finishes its execution as long as it has not been terminated by `break`, e.g.:

   ```python
   n = 0

   while n != 3:
       print(n)
       n += 1
   else:
       print(n, "else")
  
   print()
  
   for i in range(0, 3):
       print(i)
   else:
       print(i, "else")

   ```

4. The `range()` function generates a sequence of numbers. It accepts integers and returns range objects. The syntax of `range()` looks as follows: `range(start, stop, step)`, where:

   - `start` is an optional parameter specifying the starting number of the sequence (0 by default)
   - `stop` is an optional parameter specifying the end of the sequence generated (it is not included),
   - and `step` is an optional parameter specifying the difference between the numbers in the sequence (1 by default.)

Example code:

```python
for i in range(3):
    print(i, end=" ")  # Outputs: 0 1 2

for i in range(6, 1, -2):
    print(i, end=" ")  # Outputs: 6, 4, 2
```
