### Objectives

Familiarize the student with:

- using the `continue` statement in loops;
- reflecting real-life situations in computer code.

### Scenario

The `continue` statement is used to skip the current block and move ahead to the next iteration, without executing the statements inside the loop.

It can be used with both the `while` and `for` loops.

Your task here is very special: you must design a vowel eater! Write a program that uses:

- a `for` loop;
- the concept of conditional execution (_if-elif-else_)
- the `continue` statement.

Your program must:

- ask the user to enter a word;
- use `user_word = user_word.upper()` to convert the word entered by the user to upper case; we'll talk about the so-called **string methods** and the `upper()` method very soon - don't worry;
- use conditional execution and the `continue` statement to "eat" the following vowels _A, E, I, O, U_ from the inputted word;
- print the uneaten letters to the screen, each one of them on a separate line.

Test your program with the data we've provided for you.

### Test data

Sample input: `Gregory`

Expected output:

```
G
R
G
R
Y
```
<hr>

Sample input: `abstemious`

Expected output:

```
B
S
T
M
S
```
<hr>

Sample input: `IOUEA`

Expected output:

```

```
<hr>

### Solution

<details>
<summary>Check</summary>

```python
# Prompt the user to enter a word
# and assign it to the user_word variable.

user_word = input("Say a word: ").upper()

for letter in user_word:
    # Complete the body of the for loop.
    if letter == 'A':
        continue
    elif letter == 'E':
        continue
    elif letter == 'I':
        continue
    elif letter == 'O':
        continue
    elif letter == 'U':
        continue
    else:
        print(letter)
```
</details>
