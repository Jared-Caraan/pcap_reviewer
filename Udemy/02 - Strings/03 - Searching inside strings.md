## Searching inside strings

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _string-search_.

### `index()`

First, there's an index function which returns the index of the first occurrence of the given value.

<img width="605" height="97" alt="image" src="https://github.com/user-attachments/assets/975f82dc-d487-47e2-bb2a-756457e96050" /><br>

But note that this function returns the index of the first letter _A_ in the string, even if there are more letters _A_ in the string.
<hr>

### `find()`

Just like `index()`, `find()` looks for a given character or substring and returns the index of its first occurrence. 

However, there are two differences. 
1. It's safer to use. `index()` raises an error if a given value can't be found in the string. In turn, `find()` returns `-1` in such cases.
2. You can use `index()` with various types of sequences like strings or lists, but `find()` only works with strings.

<img width="907" height="465" alt="image" src="https://github.com/user-attachments/assets/325c0b72-2a72-4759-bd4d-c35e4e61df75" /><br>

<img width="538" height="139" alt="image" src="https://github.com/user-attachments/assets/a4c72f9a-a254-4c30-a94d-bac0d1ca59c3" /><br>

`find()` also has a two-argument and a three-argument version. You can use them to limit the range of characters to check in the string.

<img width="529" height="110" alt="image" src="https://github.com/user-attachments/assets/2dea8806-1823-4628-81b8-cc2af1b7c786" /><br>

This version will start looking for the `is` substring from character with index 10 inclusive until the end of the string.

And a third option with three-arguments. This three-argument version will start looking for the substring in character 10 inclusive and will stop at character 15 exclusive.

<img width="558" height="115" alt="image" src="https://github.com/user-attachments/assets/1fd8b0d5-f3a3-42af-8b17-b72bc6233376" /><br>
<hr>

### `rfind()`

There is also a function named `rfind()` which is short for right find. It works the same way as `find()`, but it starts looking for the given substring from the end of the string, not from the beginning. If there is zero or just one place in the string where the given substring occurs, this function will work the same way as `find()`. But if the given phrase is repeated more than once, it will return a different index than `find()`.

And just like with `find()`, you can use a version with one, two, or three arguments. The second and third arguments will indicate the beginning and the end of the place in the string where the occurrence should be found.
<hr>

### `isalnum()`

This method will check if the string contains only alphanumeric characters. In other words, it checks if the string only contains alphabetical characters and digits. You'll get `true` or `false` as the result of this method.

<img width="366" height="368" alt="image" src="https://github.com/user-attachments/assets/bc8b2ecc-3217-465f-b10f-390b6021cfa3" /><br>
<hr>

### `isalpha()`

This method will check if the string only contains letters.

<img width="359" height="84" alt="image" src="https://github.com/user-attachments/assets/b11081b1-1bd4-4a9b-ab49-30827dbab556" /><br>
<hr>

### `isdigit()`

This method will check if the string only contains numbers.

<img width="359" height="90" alt="image" src="https://github.com/user-attachments/assets/60b55b30-b93e-4501-9734-79862d25aada" /><br>
<hr>

### `islower()`

This method will check if the string is in lowercase.
<hr>

### `isupper()`

This method will check if the string is in uppercase.
<hr>

### `isspace()`

This method will check if the string contains whitespaces. Note that the space character is not the only white space character accepted by this method. A _newline_ character `\n` is also accepted.
<hr>
