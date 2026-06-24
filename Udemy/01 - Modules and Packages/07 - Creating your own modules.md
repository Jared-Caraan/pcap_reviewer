## Creating your own modules

So far, we have only shown you how to import modules written by other people, now it's time to create and use your own ones.

In your own project directory, preferably under the root folder, create a folder named _modules_own_module_. Enter the folder and create two _py_ files - _own_module.py_ and _main.py_.

So we have two files at the moment, _own_module_, which will be the file with our custom module and _main_py_, which will be our main application file that will import the module.
<hr>

### How modules work

Inside _main.py_, write the following code:

```python
import own_module
```

Then inside _own_module.py_, write this print statement:

```python
print("I am a module")
```

When you run _main.py_, You can see that the print invocation from the module has been executed, even though the main file only includes it as an import.

<img width="753" height="57" alt="image" src="https://github.com/user-attachments/assets/60e1b755-77a3-4bb6-8ef6-16628a631d8a" /><br>

Why is that? When a module is imported, its content is executed by Python. Automatically, Python reads whatever is inside the module line by line. If there are any print invocations, Python will execute them. If there are any variables or functions, Python will simply invoke them. Or if they are just definitions, Python will remember them so that you can invoke them in your code. This gives the module a chance to initialize some of its internal aspects. In practice, modules typically don't use functions like print to show anything to the output.

If you import the math module, it's because you want to use some of the mathematical functions and variables in your applications, not because you want the module to print something to the output. Having a module print something usually means that you have no control over it. Once you import the module, the content is automatically executed. That's why most modules only contain function and variable definitions. This way, if you import the module, nothing will be shown to the output. But because Python will run through the code of the module, you will have access to all the functions and variables defined there.

And one more important rule each module is only initialized once. Even if you have a lot of files within your application and too many of them call a given module or they call themselves Python will remember all the modules that have already been initialized.

Take a look at the diagram. In this example, there is _module_2_ that prints hello to the output. That module is imported into _module_1_ and then both modules are imported into _main_py_.

<img width="526" height="251" alt="image" src="https://github.com/user-attachments/assets/7c4ac902-7237-4a09-a886-c6c3b4616630" /><br>

Theoretically speaking, Python should first show `hello` when you import _module_1_ because _module_1_ imports _module_2_ and then Python should show `hello` for the second time when you import module_2 directly. But fortunately Python remembers the modules that are imported, which means you will see `hello` print to the output only once.
<hr>

### Module names

Each module has a special name created for us by Python - `__name__`. Note that before and after the word name there are double underscores. Python sets the value of this variable for us and the value depends on how the file is run. When the given file is run directly, the name variable is set to main. When a given file is imported as a module, the name variable is set to the module name that is it is set to the file's name without the _py_ extension.

Let's see that in practice.

Inside _own_module.py_, write this if statement:

```python
if __name__ == "__main__":
  print("File executed directly")
else:
  print("File executed as a module")
```

So now if we try to run python _main_py_, you will see `File executed as a module`.

<img width="747" height="52" alt="image" src="https://github.com/user-attachments/assets/a516f44f-a352-4995-8b86-2b62054028f6" /><br>

But if we change the invocation in the terminal window and we'll do _own_module_ you can see `File executed directly`. 

<img width="825" height="52" alt="image" src="https://github.com/user-attachments/assets/08b6333e-b19d-4df5-8118-55e742cbfb7f" /><br>

That's because this time we don't use `own_module` as a module imported in the main file. We use it directly and independently. In practice, many modules use the **name** variable to decide whether to run tests or not. Good modules don't only contain useful functions, they also contain some automated tests to verify whether the functions work correctly. Naturally, we don't want to run these tests when the module is imported in another file. However, when the module is executed independently, then the tests are activated.
<hr>

### Public and private variables

In many programming languages, you can specify whether a given variable is public or private. If it's public, then everybody can use it. If it's private, then usually only the creator of the variable can use it instead. This can be useful when the creator of a module has some internal variables that are necessary for the proper functioning of the module. But those variables may be very sensitive and the users of the module should never touch them.

The bad news is that Python has no mechanism to hide variables from the users of a module. There is, however, a convention that most people follow. If you start a variable name with one or two underscores, it means that the users of a module should never modify the variable.

```python
_my_var
__my_var
```

Keep in mind, however, that this is just a convention. The users can technically do whatever they want with the variable, the underscore simply inform them that it's a bad idea.
<hr>

### Shebang

A **shebang** (or hashbang) is a special character sequence `#!` at the very beginning of a script file. It tells the operating system which interpreter should be used to execute the code, allowing you to run a Python script as a standalone executable.

```python
#!/usr/bin/env python3
```

