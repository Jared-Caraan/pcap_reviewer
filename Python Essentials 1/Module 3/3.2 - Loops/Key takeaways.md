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
<hr>

**Exercise 1**

Create a `for` loop that counts from 0 to 10, and prints odd numbers to the screen. Use the skeleton below:

```python
for i in range(1, 11):
    # Line of code.
        # Line of code.
```

<details>
<summary>Check</summary>

Sample solution:
```python
for i in range(0, 11):
    if i % 2 != 0:
        print(i)
```
</details>

**Exercise 2**

Create a `while` loop that counts from 0 to 10, and prints odd numbers to the screen. Use the skeleton below:

```python
x = 1
while x < 11:
    # Line of code.
        # Line of code.
    # Line of code.
```

<details>
<summary>Check</summary>

Sample solution:
```python
x = 1
while x < 11:
    if x % 2 != 0:
        print(x)
    x += 1
```
</details>

**Exercise 3**

Create a program with a `for` loop and a `break` statement. The program should iterate over characters in an email address, exit the loop when it reaches the `@` symbol, and print the part before `@` on one line. Use the skeleton below:

```python
for ch in "john.smith@pythoninstitute.org":
    if ch == "@":
        # Line of code.
    # Line of code.
```

<details>
<summary>Check</summary>

Sample solution:
```python
for ch in "john.smith@pythoninstitute.org":
    if ch == "@":
        break
    print(ch, end="")
```
</details>

**Exercise 4**

Create a program with a `for` loop and a `continue` statement. The program should iterate over a string of digits, replace each `0` with `x`, and print the modified string to the screen. Use the skeleton below:

```python
for digit in "0165031806510":
    if digit == "0":
        # Line of code.
        # Line of code.
    # Line of code.
```

<details>
<summary>Check</summary>

Sample solution:
```python
for digit in "0165031806510":
    if digit == "0":
        print("x", end="")
        continue
    print(digit, end="")
```
</details>

**Exercise 5**

What is the output of the following code?

```python
n = 3

while n > 0:
    print(n + 1)
    n -= 1
else:
    print(n)
```

<details>
<summary>Check</summary>

Sample solution:
```python
4
3
2
0
```
</details>

**Exercise 6**

What is the output of the following code?

```python
n = range(4)

for num in n:
    print(num - 1)
else:
    print(num)
```

<details>
<summary>Check</summary>

Sample solution:
```python
-1
0
1
2
3
```
</details>

**Exercise 7**

What is the output of the following code?

```python
for i in range(0, 6, 3):
    print(i)
```

<details>
<summary>Check</summary>

Sample solution:
```python
0
3
```
</details>
