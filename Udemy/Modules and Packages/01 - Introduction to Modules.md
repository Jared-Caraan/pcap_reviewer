## Introduction to Modules

Python can be used for many purposes general purpose programming, data analysis or maybe automating repetitive tasks.

But no matter which field you work in, you may quickly notice that your code may grow bigger and bigger, and at some point it's difficult to keep everything in a single python file or a single Jupyter notebook.

This is especially true if you work in a team with multiple people.

<img width="843" height="499" alt="image" src="https://github.com/user-attachments/assets/831449bb-26bb-4efb-a821-e87087361a91" /><br>

In programming, we often use a process called **decomposition**. We decompose or break down our code into smaller pieces stored in separate files. This makes them easier to maintain and develop.

It's not easy to find out how to decompose your code when you're a beginner, but as you read more and more code examples during your career, you get a sort of good intuition of how to break it down.

But then just putting a code into separate files is not enough. You need to somehow inform Python that the separate files should cooperate and form a bigger code base.

The solution in Python is called **modules**. A module is simply a file that contains Python definitions and statements.

<img width="836" height="497" alt="image" src="https://github.com/user-attachments/assets/e3b360fb-70d9-48e9-855a-4a2cfac2925d" /><br>

Such a file can be imported into a second file, and once you import the module, you can use all the definitions and statements from that module in that second file.
You can also use modules created by other Python enthusiasts.

But most importantly, you can use a lot of modules that are delivered together with Python. These modules form the so called [**Python Standards Library**](https://docs.python.org/3/library/index.html) and you can go to Python documentation online to see what the library contains.

Let's take an example of a module called [`sys`](https://docs.python.org/3/library/sys.html). As you can see, it has system specific parameters and functions. If you enter the module description page, you can find all the module entities like `abiflags`, `addaudithook`, and so on.

The entities are all the definitions, like variables and methods that you can use when you decide to use this module in your code.

Among other things, there is `sys.exit`. And the description here is long and complicated. But in practice, this function closes your program by raising an exception. How can you use this function in your code then?
