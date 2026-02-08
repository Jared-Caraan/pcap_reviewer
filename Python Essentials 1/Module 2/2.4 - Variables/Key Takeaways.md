### Key takeaways

1. A **variable** is a named location reserved to store values in the memory. A variable is created or initialized automatically when you assign a value to it for the first time.
2. Each variable must have a unique name - an **identifier**. A legal identifier name must be a non-empty sequence of characters, must begin with the underscore(_), or a letter, and it cannot be a Python keyword. The first character may be followed by underscores, letters, and digits. Identifiers in Python are case-sensitive.
3. Python is a **dynamically-typed** language, which means you don't need to declare variables in it. To assign values to variables, you can use a simple assignment operator in the form of the equal (`=`) sign, i.e., `var = 1`.
4. You can also use **compound assignment operators** (shortcut operators) to modify values assigned to variables, e.g., `var += 1`, or `var /= 5 * 2.`
5. You can assign new values to already existing variables using the assignment operator or one of the compound operators, e.g.:

    ```python
    var = 2
    print(var)
    
    var = 3
    print(var)
    
    var += 1
    print(var)
    ```
6. You can combine text and variables using the `+` operator, and use the `print()` function to output strings and variables, e.g.:

    ```python
    var = "007"
    print("Agent " + var)
    ```
<hr>

#### Exercise 1

What is the output of the following snippet?

```python
var = 2
var = 3
print(var)
```

<details>
<summary>Check</summary>

`3`
</details>
<hr>

#### Exercise 2

Which of the following variable names are <ins>illegal</ins> in Python?

```python
my_var
m
101
averylongvariablename
m101
m 101
Del
del
```

<details>
<summary>Check</summary>

`101`, `m 101`, `del`
</details>
<hr>

#### Exercise 3

What is the output of the following snippet?

```python
a = '1'
b = "1"
print(a + b)
```

<details>
<summary>Check</summary>

`11`
</details>
<hr>

#### Exercise 4

What is the output of the following snippet?

```python
a = 6
b = 3
a /= 2 * b
print(a)
```

<details>
<summary>Check</summary>

`1.0`
</details>
<hr>
