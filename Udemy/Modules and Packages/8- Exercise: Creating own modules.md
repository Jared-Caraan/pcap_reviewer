### Creating own modules

Let's create a simple program that uses some modularity. You are given three files:

1. **string_utils.py** (_note singular "string"_)
2. **strings_utils.py** (_note plural "strings"_)
3. **main_program.py**

Your task is to fill all three files with some code according to the requirements:

1. **string_utils.py**: this file should contain a function named `halve_string` that accepts a single argument: `input_string`. Given a string, the function should return a tuple with two string elements: the first element should contain the first half of the string, the second element should contain the second half of the string. For strings with an odd count of characters, the first element should also contain the middle character.

   Example 1: `halve_string('Mark')` should return `('Ma', 'rk')`
   Example 2: `halve_string('Lydia')` should return `('Lyd', 'ia')`

2. **strings_utils.py**: this file should import **string_utils** as a module and then use the function from point (1) to create its own function named `halve_strings` that accepts a single argument: a list of strings `string_list`. Given a list of strings, the function should return a list of tuples with halved strings, just like we explained in point (1).

    Example: `halve_strings(['Mark', 'Lydia'])` should return `[('Ma', 'rk'), ('Lyd', 'ia')]`

3. **main_program.py**: this file should import **strings_utils** as a module, use the function from point (2) on the list provided in the editor (`quotes`), and print the return value of the function.

**Files**

<details>
<summary>main_program.py</summary>

```python
quotes = ['Being happy never goes out of style.',
'Life is either a great adventure or nothing.',
'All you need in this life is ignorance and confidence; then success is sure.',
'All your life, you will be faced with a choice. You can choose love or hate... I choose love.',
'The time is always right to do what is right.']
```
</details>

<details>
<summary>string_utils.py</summary>

```python
```
</details>

<details>
<summary>strings_utils.py</summary>

```python
```
</details>
<hr>

### Solution

<details>
<summary>main_program.py</summary>

```python
import strings_utils

quotes = ['Being happy never goes out of style.',
'Life is either a great adventure or nothing.',
'All you need in this life is ignorance and confidence; then success is sure.',
'All your life, you will be faced with a choice. You can choose love or hate... I choose love.',
'The time is always right to do what is right.']

print(strings_utils.halve_strings(quotes))
```
</details>

<details>
<summary>string_utils.py</summary>

```python
def halve_string(input_string):
    
    half_string = len(input_string)//2
    
    if len(input_string) % 2 == 0:
        return input_string[0:half_string], input_string[half_string: len(input_string)]
    else:
        return input_string[0:(half_string)+1], input_string[(half_string)+1: len(input_string)]
```
</details>

<details>
<summary>strings_utils.py</summary>

```python
import string_utils

def halve_strings(string_list):
    return [string_utils.halve_string(i) for i in string_list]
```
</details>
