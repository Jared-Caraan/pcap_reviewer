## The finally keyword

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exceptions-finally_.

Python offers an additional keyword that can be used with try-accept blocks - `finally`. `finally` must be the very last branch of the code intended for handling exceptions. It must appear even after the `else` block. `else` and `finally` are not dependent on each other, you can have both of them.

The general rule is that the `finally` block is executed **always**, no matter if an exception is raised or not, no matter if a raised exception is handled or not, the finally block will always execute. In real-life programming, `finally` blocks are typically used when we work with some external resources, such as databases or text files.

For instance, when we want to retrieve some data from a database, we first need to open a connection to the database, then retrieve the data and then close the connection. It's then a good idea to close the connection in a `finally` block, no matter if our code succeeds or not. No matter if we manage to retrieve the data or we get a connection error, we should always close the connection to the database to limit the amount of memory that the machine uses.

### Sample Code

<img width="576" height="452" alt="image" src="https://github.com/user-attachments/assets/cf4e8fdd-3679-4349-9380-c69872835e36" /><br>

So note that in both situations the `finally` block is executed before the function finishes and returns the actual number.
