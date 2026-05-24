## Basic string operations

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _string-basic-operations_.

### Review

Keep in mind that python strings are immutable sequences. It means that you can, for example, use the `len()` function to get the number of characters in a string. If you have an empty string, its length will be zero.

<img width="336" height="182" alt="image" src="https://github.com/user-attachments/assets/33a4c21a-cf6f-4cf9-a72b-82e9accaa8f9" /><br>

You can also use brackets with an index to access any given character in a string. Remember that indexes start at zero. You can also use slicing to get a substring.

<img width="411" height="267" alt="image" src="https://github.com/user-attachments/assets/ec3dfd30-f599-4e93-930a-8b57463954d5" /><br>

Keep in mind that certain characters are special characters and that you need to put a backslash before them. One of them is an apostrophe.

<img width="394" height="103" alt="image" src="https://github.com/user-attachments/assets/97a9b426-2507-47a9-9e55-aea6b0a63bfd" /><br>

Keep in mind that the escape character is not included in the string length. It is not encoded as a character in the string internally. It's just a piece of info for Python to know that the character coming after the backslash is a special one.
<hr>

### `ord()` and `chr()`

Remember how we talked about ASCII and Unicode encoding? We mentioned that each character has a certain number assigned to it, also known as a **code point**. To get to know the code point for a given character, you can use the `ord()` function. This function can only accept a one character string. If you try to provide anything else, you'll get an error.

A reverse function is `chr()`. If you provide a number as its argument, you will find the character behind it.

<img width="266" height="187" alt="image" src="https://github.com/user-attachments/assets/4fff9990-37be-4daf-98be-20338fc1d3c0" /><br>
<hr>

### Multi-line String

A python allows you to use multi-line strings too, but you need to be careful. The syntax is a bit different. You need to start and end the string with triple quotes.

<img width="422" height="174" alt="image" src="https://github.com/user-attachments/assets/fa0ab5c0-d033-4671-bf5f-0aee145128c5" /><br>

Now, let's see how many characters there are in this string. You can see that there are six characters on the first line, including a space between the words. There are another six characters on the second line. This gives 12, but Python shows 13. How is that possible? The answer is an invisible character between line one and two, which instructs Python that a new line should be introduced without the special character. Python would simply interpret this string as line one, line two with no spaces between them. The special character is called **Line Feed** and it is frequently expressed as backslash, and this character is included in the length of the string and has a length of one.
<hr>

### String concatenation

Strings can also be concatenated or in other words, joint with the plus sign. They can also be multiplied - repeated multiple times using the asterisk sign and an integer.

<img width="308" height="179" alt="image" src="https://github.com/user-attachments/assets/3c23f3d3-277a-44be-b764-437e9ae2c430" /><br>

> [!NOTE]
> This phenomenon where the same plus operator can be used for different kinds of data to produce different results is called **operator overloading**.
<hr>

### String iteration

You can also iterate over a string.

<img width="740" height="105" alt="image" src="https://github.com/user-attachments/assets/cfdc7d23-7f1d-4918-aba8-1bde2fd7527a" /><br>
<hr>

### Immutability

Keep in mind that python strings are immutable. This means that once you create a given string, you can't change it. You can only replace it with a new one.

For example, you can't use the `del` keyword to delete a character from a string. You can't use insert or append either, so there is no way to add a new character into a string either.

<img width="907" height="260" alt="image" src="https://github.com/user-attachments/assets/b7114852-abd8-4f70-a06e-b4de046c59b4" /><br>
<hr>

### Less common functions

For instance, the `min()` function looks for the smallest element in the sequence. How will it work with a string?

<img width="547" height="93" alt="image" src="https://github.com/user-attachments/assets/e73ad11b-3f74-4987-b71c-59739a17b1a5" /><br>

That's because if we convert all the characters into numbers according to the ASCII encoding, the letter `a` will have the lowest number.

Consequently, the `max()` function finds the character with the highest code point.
