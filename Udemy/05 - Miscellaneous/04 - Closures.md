## Closures

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-closures_.

A closure is a technique for implementing lexical scoped name binding in the language with first class functions. A more digestible definition would be something like this: a closure is a function defined inside another function that remembers the values of the outer function.

### Example

<img width="441" height="311" alt="image" src="https://github.com/user-attachments/assets/75a1d72a-c365-4794-9fd3-cb0aa1ef8e80" /><br>

We define a function named `greet`. This function takes a single argument, a text value. Next, inside the `greet` function, we define another function - `print_greet`. `print_greet` is called a nested function. As you can see, you can nest functions in Python the same way that you can nest for loops or if statements. This nested function doesn't take any arguments inside. It prints the `text` variable to the output. That's an important step. As you can see, the nested function has access to the variables available in the outer function. So even though `print_greet` doesn't get `text` as an argument, it can access the variable because the variable is available in the outer function. That nested function `print_greet` becomes a **closure** the moment it references a variable from the outer function. If we didn't reference any variables from the `greet` function, `print_greet` would simply be called a **nested function**. And now the second interesting thing happens - we return the closure from the outer function. Note that we don't add brackets to the closure name. That's because we don't want to invoke the function, we simply want to return it.

In Python, whenever you add a pair of round brackets, be it with or without arguments inside you're instructing Python to call a function. Without the brackets, we simply return the nested function without calling it. Because we return a value from the outer function, that value can be saved into a variable.

We call the `greet` function with a single argument. And we store the result in the `say_hello` variable. Note that at this point nothing has been printed yet. The print invocation is contained inside the `print_greet` closure. But the closure was never called, so there's nothing printed to the output yet.

On the last line, we add a pair of round brackets to the variable name. This means try to invoke whatever is contained inside the `say_hello` variable and because `say_hello` contains a closure, that closure is invoked. The closure contains a print statement so we can see something printed to the output.

The closure remembers the value of text. The closure knows that it should print _hello_ to the output, even though we don't pass anything when we call the closure on the last line. That's a very important feature of closures. They can store values from the outer functions, even though these functions have finished executing and the values should be, theoretically speaking, already destroyed.

Such variables, variables that should be already destroyed but are still available in a closure are called **free variables**.
<hr>

### Another example

<img width="615" height="476" alt="image" src="https://github.com/user-attachments/assets/ef95b008-6ce5-4e96-b713-e36368a0190a" /><br>

These variables now contain the same closure with two different values for `x` - 5 and 12. Later in the code, we can call each closure version and provide an argument which will be used as the second number, the `y` parameter in the inner function. Here, the closure remembers the first number and multiplies it by the second number provided.

Closures can sometimes replace small classes. If you have a class that only has one custom method, you can typically replace it with a closure and the code will be shorter to read.
<hr>

### Multiple Closures

If you have multiple functions defined inside an outer function, the classic way to access or call them depends on how the outer function returns them. Since a function can only hit one return statement, you typically return the inner functions wrapped inside a tuple, list, or dictionary, or you return a coordinator function.

Here is how you would set it up and call them:

#### Method 1: Returning a Dictionary (Most Readable)

Returning a dictionary allows you to call the inner functions using string keys, making your code very clear.

```python
def make_math_closure(x):
    def multiply(y):
        return x * y

    def add(y):
        return x + y

    # Return both inner functions as a dictionary
    return {"mult": multiply, "plus": add}


# 1. Initialize the closure with x = 5
my_math = make_math_closure(5)

# 2. Call the specific inner functions using their keys
print(my_math["mult"](10))  # Outputs: 50  (5 * 10)
print(my_math["plus"](10))  # Outputs: 15  (5 + 10)
```
<hr>

#### Method 2: Returning a Tuple (Unpacking)

You can return the functions as a tuple and unpack them into separate variables right away.

```python
def make_math_closure(x):
    def multiply(y):
        return x * y

    def add(y):
        return x + y

    return multiply, add  # Returns a tuple: (multiply, add)


# Initialize and unpack into two separate variable names
times_five, plus_five = make_math_closure(5)

# Call them independently
print(times_five(10))  # Outputs: 50
print(plus_five(10))  # Outputs: 15
```
<hr>

#### The "Dispatch" Function (Object-Like)

Another advanced pattern is to return a single "master" inner function that decides which operations to run based on an argument you pass to it.

```python
def make_math_closure(x):
    def multiply(y):
        return x * y

    def add(y):
        return x + y

    # The dispatch function acts as a router
    def dispatch(action):
        if action == "multiply":
            return multiply
        elif action == "add":
            return add

    return dispatch


# Initialize
calc = make_math_closure(5)

# Call the second inner function by routing through dispatch
print(calc("add")(10))  # Outputs: 15
```
