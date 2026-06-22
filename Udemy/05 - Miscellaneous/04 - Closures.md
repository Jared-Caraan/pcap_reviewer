## Closures

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-closures_.

A closure is a technique for implementing lexical scoped name binding in the language with first class functions. A more digestible definition would be something like this: a closure is a function defined inside another function that remembers the values of the outer function.

## Example

<img width="441" height="311" alt="image" src="https://github.com/user-attachments/assets/75a1d72a-c365-4794-9fd3-cb0aa1ef8e80" /><br>

We define a function named `greet`. This function takes a single argument, a text value. Next, inside the `greet` function, we define another function - `print_greet`. `print_greet` is called a nested function. As you can see, you can nest functions in Python the same way that you can nest for loops or if statements. This nested function doesn't take any arguments inside. It prints the `text` variable to the output. That's an important step. As you can see, the nested function has access to the variables available in the outer function. So even though `print_greet` doesn't get `text` as an argument, it can access the variable because the variable is available in the outer function. That nested function `print_greet` becomes a **closure** the moment it references a variable from the outer function. If we didn't reference any variables from the `greet` function, `print_greet` would simply be called a **nested function**. And now the second interesting thing happens - we return the closure from the outer function. Note that we don't add brackets to the closure name. That's because we don't want to invoke the function, we simply want to return it.
