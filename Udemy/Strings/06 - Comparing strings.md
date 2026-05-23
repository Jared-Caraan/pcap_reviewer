## Comparing strings

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _string-comparisons_.

Python allows you to compare strings using the same operators like you know from numbers such as `==`, `!=`, `<`, `<=`, `>`, `>=`.

### equal / not equal

<img width="385" height="388" alt="image" src="https://github.com/user-attachments/assets/b99b0ecc-bb97-4337-b864-6239a6e7987f" /><br>

So two strings are equal if and only if they are identical, they need to contain the exactly same characters. If the letters are the same, but one of them is uppercase and the other one's lowercase, then the strings are considered not equal.
<hr>

### greater than / less than

What does it mean when one string is greater than the other? Remember how we taught you that internally, each character in a string is represented by a number named code point. Python will simply compare the numbers behind the letters. When there are two strings, Python compares the characters at the same indexes in both strings until it finds a difference.

So for instance, in this case, the first differing characters are lowercase P and uppercase P. So Python checks the ASCII codes for those two characters.

<img width="516" height="86" alt="image" src="https://github.com/user-attachments/assets/b3f9965c-8c68-486b-ac68-3da14d26f0c9" /><br>

<img width="426" height="294" alt="image" src="https://github.com/user-attachments/assets/d3b7fc12-31e2-4c15-b588-2b9e0ff6d12d" /><br>

For uppercase P, it's 80. For lowercase P, it's 112. 112 is greater than 80. So Python treats this string with lowercase p as greater than the string with uppercase p.

And what happens if one of the strings is identical with the other one but has some extra characters at the end? The longer string is then considered greater.

<img width="400" height="101" alt="image" src="https://github.com/user-attachments/assets/9d9edf07-09c2-4714-8d61-6640654065ef" /><br>

But remember that this rule only applies if the shortest string is identical with the beginning of the longest string. If it's not, then Python checks the first differing indexes and compares the characters. The length of the string doesn't matter.

<img width="367" height="85" alt="image" src="https://github.com/user-attachments/assets/1f50c21f-9f20-43e1-95a7-da03672b7724" /><br>

The string `Z` is shorter than `Pythonist`, but the first differing character is `Z` versus `P` and `Z` has a greater code, so the whole string is considered greater.

Now keep in mind that if your string contains digits only, it's not treated as a number, it is compared character by character.

<img width="276" height="92" alt="image" src="https://github.com/user-attachments/assets/4dbc43f0-f888-4196-8fad-14addce56e94" /><br>

So for instance. This evaluation gives false. That's because Python searches for the first different character in both strings, in this case at index zero. There is number `2` in the first string and number `8` in the second string. `8` is greater than `2`. So Python treats string `8` as greater than string `20`. 
<hr>

## Mixed Comparison

But what happens when you try to compare a string with a number? The only two operators that you can use are equal to and not equal to. Note that a string in Python can never be equal to a number. So you will always get false.

<img width="288" height="190" alt="image" src="https://github.com/user-attachments/assets/1075c685-11e9-46e9-83fc-a8c10f2f9c27" /><br>

If you try any other operator like greater than you will get a type error.

<img width="896" height="212" alt="image" src="https://github.com/user-attachments/assets/24b9b5fe-dcb4-4fa5-8eec-e3a29fc57755" />

