## Importing Modules

1. Let's create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/).
2. We'll call it _modules-import_, and now we'll write the following line.
3. `import sys` - this simple command tells Python to look at the module named `sys` and make available all the entities in that module. By convention, all input statements should be placed at the top of a python file.
   <img width="883" height="290" alt="image" src="https://github.com/user-attachments/assets/03683888-763b-4079-9d3d-a3308840ffab" />
4. If you have more than one module to import, you've got two options.
   - Option A is to use to import statements like this, `import sys` and now let's say `import math`.
     <img width="325" height="89" alt="image" src="https://github.com/user-attachments/assets/855d9181-408f-41d1-9e95-0e537cb52427" />
   - Or you can do option B - `import sys, math` so you can separate the module names with commas.
     <img width="367" height="59" alt="image" src="https://github.com/user-attachments/assets/4c488625-700a-4b83-bb7e-93653848ee59" />
5. Now we want to see what entities we can use. One way is to browse the [documentation](https://docs.python.org/3/library/sys.html) available online like we did in the previous section. But you can also use a special function named `dir`. Here you can see all the entities that this module makes available. In other words, all the variables and the functions that you can use in your code.
   <img width="1682" height="499" alt="image" src="https://github.com/user-attachments/assets/f640f878-0cfc-4b7f-b6f4-94818590098d" />
6. And now if you want to use a particular function like the `exit` function, you should start by writing the module name followed by a dot, and now the name of the function. If we run our little program, you can see that the exception was raised and the program was interrupted. That's exactly what `sys.exit()` does.
   <img width="1674" height="349" alt="image" src="https://github.com/user-attachments/assets/8c99abce-d678-4046-bb61-37cdd4cad403" />
7. What happens if you try to use an entity from a module that doesn't exist? You can see an attribute error.
   <img width="1034" height="342" alt="image" src="https://github.com/user-attachments/assets/2ece28b7-e58c-4ea1-9973-e2cd38fc70c5" />

<hr>

Now, you may be wondering, why do you need to specify the module name?

Actually, that's a good feature to help you this way. If you have your own function with the very same name, the two won't be messed up.

So let's say that, we import this `sys` module, but this time we come up with our own `exit` function, which instead of raising an exception, it prints - `I want to exit to the output`.

<img width="857" height="365" alt="image" src="https://github.com/user-attachments/assets/e4ef3ac7-3739-4a3b-86bf-5fade1f5f63e" /><br>

As you can see, first, the custom made `exit` function was invoked and we saw the `I want to exit` statement to the output and then the actual `exit` function from the `sys` module was called and an exception was raised. So the first invocation is our own function that just prints some text to the output. And the second invocation is the actual exit function from the `sys` module.

Thanks to this feature, thanks to the `sys` prefix - python can distinguish between your own code and the code from the imported modules. We can say that the `sys` module has its own namespace. By starting the line with `sys`, we inform Python that it should look for the `exit` function within inside the `sys` namespace.
<hr>

Having to state the namespace is generally considered a good feature, but you may sometimes need to use one particular function from one particular module over and over again. In such cases you'd like to omit the namespace. Python allows that, but you need to change the import statement. Here we could specify the exact entities from the module we are interested in. By using this syntax, we no longer need to use the `sys` namespace.
<img width="866" height="216" alt="image" src="https://github.com/user-attachments/assets/8eebd00f-243d-4f69-b081-0315bd45a6e3" /><br>

But what happens if you input a function named `exit` using this syntax, but you also have your own `exit` function.
<img width="483" height="245" alt="image" src="https://github.com/user-attachments/assets/dff45958-ad65-49af-9e1b-3f1d82701e10" /><br>

As you can see, your own function replaced the function imported from the module. That's why you need to watch out when you use the `from module import` syntax. If you have something with the very same name, actually, whatever you try to import will be overwritten. It will be replaced by your custom code.
<hr>

You can also use an asterisk to import everything. But keep in mind, this is quite dangerous. There may be many entities in that module that have identical names with your own functions and variables. Using the asterisk may mean some of the functions will be replaced and a lot of conflicts will appear. That's why this line is not recommended for use.

<img width="408" height="88" alt="image" src="https://github.com/user-attachments/assets/7377cffa-f68d-4737-8540-da9eb01acb30" />
<hr>

And now a tricky question. What's the difference between these two lines?

<img width="403" height="94" alt="image" src="https://github.com/user-attachments/assets/640e8bb8-a40c-4644-9236-2ab278dfd61b" /><br>

Both statements input all the entities from the `sys` module. But if you use the first option, you need to remember about the `sys.` prefix, about the `sys` namespace, so you need to add `sys.`. In the second option, you don't need to start with `sys.`, but you may get a lot of conflicting names in the end.
<hr>

Finally, you may also give aliases to whole modules or individual module entities.

<img width="892" height="221" alt="image" src="https://github.com/user-attachments/assets/bd5a2a27-b596-43f8-a21b-c60e4f5894c0" /><br>

And everything works fine. So instead of `sys.exit()`, you can now use the shorter version of `s.exit()`. This may come in handy if you work with modules that have really long names.
<hr>

You can also give aliases to individual entities.
<img width="877" height="212" alt="image" src="https://github.com/user-attachments/assets/63a9493f-2d28-45b5-96c9-25f0f18b7298" />

You may use an alias if there is a very long name of a module function or variable, just try not to overuse this feature. People generally get accustomed to the function names from popular modules, so changing all of the names in your code may actually lead to lower readability.
