## Predefined streams

When you start any program in Python, there are actually three predefined streams that don't need any preparation. What's more, they are not associated with any files. You do need to call the `open` function to get these and they are ready made for you. If you want to use them, you need to input the `sys` module using the input `sys` command. The names of the three streams are - `sys.stdin`, `sys.stdout`, and `sys.stderr`.

### `sys.stdin`

We'll start with `sys.stdin`, which means **standard input**. It's a special kind of stream that by default reads user input from the keyboard, not from a file. The `input` function that you've used many times reads data from this stream by default.

<img width="597" height="285" alt="image" src="https://github.com/user-attachments/assets/43a591be-9578-4cd2-939b-26d3f08e3f47" /><br>

So this specific code will read whatever you put in the console line by line and print it to the output. And if you type `q`, we will exit the loop and quit the program, but before that we will print a short message. So by default you will also get a new line character at the end of each line that you enter. So we also use the `rstrip` function to get rid of the new line character so we can check if the line equals the `q` character.

<img width="762" height="458" alt="image" src="https://github.com/user-attachments/assets/12446849-a13f-4577-a5cd-b0708c16b494" /><br>
<hr>

### `sys.stdout`

The second predefined stream is `sys.stdout` and it stands for **standard output**.

<img width="737" height="917" alt="image" src="https://github.com/user-attachments/assets/fc5e01b6-2ae7-4c84-bb83-a325d668a9f8" /><br>

If you want to print an integer to the output using this technique, you would have to turn it into a string first.
<hr>

### `sys.stderr`

Finally, the third predefined stream is `sys.stderr`, which stands for Standard Error. Standard error is very similar to standard output. It also outputs strings to the console. There is just a semantic distinction. Useful results produced by our programs should be directed to the standard output, while error messages should be directed to the standard error.
