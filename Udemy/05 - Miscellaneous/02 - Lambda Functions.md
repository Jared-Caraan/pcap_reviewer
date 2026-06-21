## Lambda Functions

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-lambdas_.

Lambda functions in Python are used to simplify code to make it easier to understand, shorter, and clearer.

A typical function in python is defined like this.

<img width="602" height="125" alt="image" src="https://github.com/user-attachments/assets/21d80702-c07a-43c9-b8ef-aa4c895752ce" /><br>

A lambda function in Python in turn looks something like this.

<img width="532" height="62" alt="image" src="https://github.com/user-attachments/assets/4053a3af-abbe-476b-a3af-521a304b6091" /><br>

The two major differences that stick out almost immediately are that a function always has a name. A lambda in turn can be used without giving it any name. The second difference is that a lambda can only contain a single instruction.

<img width="401" height="137" alt="image" src="https://github.com/user-attachments/assets/97214007-ada2-47de-93e5-d6b794bbf8cd" /><br>

Again, note two things. First of all, the lambda version is much shorter. Second of all, the lambda version does not need the return keyword and of course the variables can be named differentially.

But how do we call the lambda if it doesn't have a name?

<img width="557" height="150" alt="image" src="https://github.com/user-attachments/assets/1d696a0d-fa81-4b20-bb51-0e6f72d1e074" /><br>

There are a few situations where lambdas come in handy. One of the superpowers is that they can be passed around just like variables.

<img width="491" height="100" alt="image" src="https://github.com/user-attachments/assets/a5d458de-85b2-4e11-9a04-b571dea7cc80" /><br>

This function takes a sequence of elements and then for each element it prints something. This something that is printed to the output is actually the result of a function call. And here's the tricky part. It's not a specific function that we call. It can be any function that is passed to the `apply_func` function as a parameter named `func`.

<img width="517" height="198" alt="image" src="https://github.com/user-attachments/assets/8330eb40-fcdd-45d1-a44c-34b0548940e9" /><br>

The first argument contains the elements to iterate inside `apply_func` which are the numbers from 1 to 5. Now for each of the elements, we want to apply the function passed as the second parameter. The function is a lambda that we saved in the `my_func` variable. It takes one argument and returns the argument squared.

Now in the output we can actually see that for each element, the `apply_func` function used the lambda to calculate the second power and then it's printed the result.

The beautiful thing about the `apply_func` function is that it can work with so many different lambda types.

<img width="535" height="197" alt="image" src="https://github.com/user-attachments/assets/0a40997b-438d-4a83-894a-3b6053ce127e" /><br>

<img width="521" height="197" alt="image" src="https://github.com/user-attachments/assets/07b0bd49-053c-49ee-864a-2f921a0d9988" /><br>

You don't even need to save the lambda into a variable, as we only need at once.

<img width="612" height="180" alt="image" src="https://github.com/user-attachments/assets/e58a1bef-c9de-4597-b278-44e5fab8715b" /><br>

Note that the lambda is not saved anywhere in this setup. Once this line is executed, the lambda is lost and you can't reuse it later in the code.

But this is exactly what we needed. A simple way to define a function in line with the function invocation itself. That's the beauty of lambdas. They allow you to write shorter, clearer code without defining unnecessary variables.

Lambda functions are sometimes called functions without names or anonymous functions.
