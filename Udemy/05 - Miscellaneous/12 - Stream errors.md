## Stream errors

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-file-diagnose-errors_.

We already know that we can get nasty exceptions when working with files: A file may not exist, we may not have the proper permissions to open it and so on. So far we've used very simplified try except statements. And we used a very general exception type, simply named `Exception`.

<img width="910" height="200" alt="image" src="https://github.com/user-attachments/assets/c5afdbfd-cebd-42cd-af66-29a0f4c57f63" /><br>

Can you see that part in square brackets? It turns out that each problem that we may encounter when working with files has a specific number assigned. And if you want to access that number, you can simply do the following:

<img width="568" height="197" alt="image" src="https://github.com/user-attachments/assets/a256ae2d-28be-41c8-bb46-bcea9d450e52" /><br>

If you're curious about all the possible error numbers, you can take a look at the [documentation](https://docs.python.org/3/library/errno.html).

Interestingly, Python provides a function in the `os` module that accepts the error number and then prints a nice and short text explanation of what actually went wrong.

<img width="537" height="252" alt="image" src="https://github.com/user-attachments/assets/14ed199c-1a5e-42b7-83e8-4726c931611c" /><br>
