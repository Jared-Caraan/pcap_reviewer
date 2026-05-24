## Working with strings

John loves analysing textual information. He often reads short stories and then tries to find the longest word in such stories. Doing this manually takes a long time so we'd like to help him automate the task.

_Note: You are provided an example of a short story in the code editor. The example story should not be part of your solution: it is just there to help you._

Write a function named `get_longest_word` which accepts a single string argument. The function should return the longest word in the given string. Assume that words in a string can be separated with **spaces**, **commas**, **new line characters** or **full stops**. This means that abbreviated forms with apostrophes (e.g. `I'm`) are considered to be a single word. If there is more than one word with the maximum number of characters, return the first such word that exists in the string.

Example: For input `Once I'm awaken, I'll sacrifice your soul to the ruler of darkness.` the output should be `sacrifice`.

<details>
<summary>Initial Script</summary>

**exercise.py**
```python
sample_story = '''Once upon a time, there was a beginner programmer named Alice who was eager to learn Python. She tried to learn from books, but found it difficult to grasp the concepts. One day, she stumbled upon an online course.

Alice was thrilled. The course was taught by a well-known programmer who made the lessons interesting and easy to understand. The course covered everything a beginner programmer needed, and Alice was finally able to understand how to code in Python.'''
```
</details>
<hr>
<details>
<summary>Solution</summary>

**exercise.py**
```python
sample_story = '''Once upon a time, there was a beginner programmer named Alice who was eager to learn Python. She tried to learn from books, but found it difficult to grasp the concepts. One day, she stumbled upon an online course.

Alice was thrilled. The course was taught by a well-known programmer who made the lessons interesting and easy to understand. The course covered everything a beginner programmer needed, and Alice was finally able to understand how to code in Python.'''

def get_longest_word(text):
    # Replace specified separators (commas, newlines, full stops) with a standard space
    normalized_text = text.replace(',', ' ').replace('\n', ' ').replace('.', ' ')
    
    # Split the string by spaces to get individual words
    words = normalized_text.split()
    
    # If the text is empty or contains no words, return an empty string
    if not words:
        return ""
    
    # Find the longest word. 
    # Python's max() is stable, meaning it will return the *first* occurrence 
    # of the maximum length if there are ties.
    longest_word = max(words, key=len)
    
    return longest_word
```
</details>
