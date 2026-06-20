## Assertions

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _assertions_.

So far we've only seen Python functions raise exceptions for us, but what if we want to raise exceptions by ourselves?

### Example

Assertions are certain assumptions in our program that we think should always be true.

<img width="595" height="93" alt="image" src="https://github.com/user-attachments/assets/45c1243b-eafa-470c-a3cf-d6abdf15969b" /><br>

This simple function uses a new keyword - `assert`. After this keyword, we put one or more conditions inside round brackets. These are conditions that we assume should always be true for this specific function to work correctly. If the condition or conditions are true, Python simply moves on to the next line. But if the condition is not true, then Python shows an error with the error message that we specify after the comma.
<hr>

### AssertionError

<img width="928" height="518" alt="image" src="https://github.com/user-attachments/assets/87b3b110-d514-450a-9037-57a658b99774" /><br>

And a new kind of exception appeared - `AssertionError`. It is always called when we use the keyword `assert` and the condition provided within the brackets is not satisfied.
<hr>

### When to Use

In general, assertions are used for debugging and testing your code. You can add assertions as sanity checks at the beginning of a function to make sure that it receives correct data. Assertions are also sometimes used to document your code. This way you can communicate to other developers what you expect in your functions. 

On the other hand, you should **not** use assertions for validating user input. That's because it is possible to turn off assertions when you publish a program to your users. Turning off assertions in this case would mean that you lose all the code that validates user input. Apart from that, assertions are not an error handling tool. The purpose is to notify you about bugs during development so you can catch and fix bugs quickly. Because of that, you should not write code that handles assertion errors using try-except assertion error blocks.
