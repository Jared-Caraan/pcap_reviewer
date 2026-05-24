## Using packages in Python

If you only have a few modules, then keeping them in a single location within a single folder is not a bad idea. However, you may quickly run into problems when you have tens or even hundreds of modules. Keeping them in a single folder will quickly lead to chaos. That's why the authors of Python came up with a simple concept of packages.

A **package** is a container or a box for similar modules. This way you can easily organize modules into categories. Creating packages in Python is extremely simple. You just need to create a folder on your hard drive and name it. You can also have multiple folders at the same level, or you can have folders inside folders. Python will automatically treat them as subpackages in packages.
<hr>

### Sample directory

In your local directory, achieve the structure similar to the image below.

<img width="183" height="226" alt="image" src="https://github.com/user-attachments/assets/b51217eb-b161-46b2-8f50-555d43397931" /><br>

So inside the _project_modules_ there are three subpackages - _communication_, _core_, and _messaging_. Inside the _communication_ package there is a module named _com.py_. Inside the package _core_ there is a module named _util.py_ and another subpackage named _additional_ with _security.py_ inside. And at the very end we've got _messaging_ with two modules _event.py_ and _queue.py_.

Along the level of _project_modules_ package, create the _main-packages.py_.

Here's the content for each sub-files:

<details>
<summary>com.py</summary>

```python
def my_fun():
  print("a")
```
</details>

From _main-packages.py_, you can use the functions inside _com.py_ like this:

<img width="1115" height="846" alt="image" src="https://github.com/user-attachments/assets/1e70d07b-7d99-4da8-af3b-eae53e6b6439" /><br>

Now, if you don't want to write such a long name for the function with all the packages and the module name, you can use a different kind of import line.

<img width="712" height="846" alt="image" src="https://github.com/user-attachments/assets/f5d07872-960f-4361-bb4c-a09571f68f9e" /><br>

One important thing you need to remember is that you must always provide specific modules in the import statements. Unfortunately for the example code below, Python doesn't work like this. You can technically import the package itself like this without specifying any modules, but this has no practical usage. The modules will not be imported. So you can see that the import statement actually instructs Python to import that package itself, not the modules inside the package.

<img width="880" height="902" alt="image" src="https://github.com/user-attachments/assets/14ba512c-e44c-4d8e-8cbf-5f17cfd1e066" /><br>
<hr>

### `__init__.py`

It's a very special kind of file that you can add in a package directory when you create a package. This file can be used to initialize the package if this is necessary. This file is executed by Python when any of the packages modules is or are imported. The file can also be empty and then Python will simply ignore it.

In recent versions of Python, the `__init__.py` file has become optional. Previously it had to be present for every package. Without the file, Python did not treat a given folder as a package. Starting from Python 3.3, you don't need this file to create a package. All you need is to create a directory in your operating system and Python will automatically treat that as a package. But you can of course still use any `__init__.py` files if you need some sort of initialization for your modules.
