### Objectives

Familiarize the student with:

- using the `continue` statement in loops;
- modifying and upgrading the existing code;
- reflecting real-life situations in computer code.

### Scenario

Your task here is even more special than before: you must redesign the (ugly) vowel eater from the previous lab and create a better, upgraded (pretty) vowel eater! Write a program that uses:

- a `for` loop;
- the concept of conditional execution (_if-elif-else_)
- the `continue` statement.

Your program must:

- ask the user to enter a word;
- use `user_word = user_word.upper()` to convert the word entered by the user to upper case; we'll talk about the so-called **string methods** and the `upper()` method very soon - don't worry;
- use conditional execution and the `continue` statement to "eat" the following vowels _A, E, I, O, U_ from the inputted word;
- assign the uneaten letters to the `word_without_vowels` variable and print the variable to the screen.

Look at the code in the editor. We've created `word_without_vowels` and assigned an empty string to it. Use concatenation operation to ask Python to combine selected letters into a longer string during subsequent loop turns, and assign it to the `word_without_vowels` variable.

Test your program with the data we've provided for you.
