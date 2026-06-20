## Propagating Exceptions

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exception-propagation_.

<img width="807" height="686" alt="image" src="https://github.com/user-attachments/assets/a3498310-785a-4be5-81e0-f93f9b093fff" /><br>

The rule is that exceptions are propagated through functions in Python. If `get_user_bday` calls `get_day` and it raises an exception but it doesn't have a try-except block, `get_user_bday` can handle that exception.

If a function that raises an exception doesn't have a try-except block, that exception is propagated to the function that called it. If that function doesn't have a try-except block either, the exception is propagated again until there finally is a try-except block somewhere in the function call chain. If no try except block can be found anywhere, Python will simply show a nasty error message that you've already seen many times.

<img width="872" height="347" alt="image" src="https://github.com/user-attachments/assets/9852e332-e757-400f-a319-13432089f8ce" /><br>
