### Key takeaways – Exceptions

1. In Python, there is a distinction between two kinds of errors:

   - **syntax errors** (parsing errors), which occur when the parser comes across a statement that is incorrect. For example: \
     Trying to execute the following line:

     ```python
     print("Hello, World!)
     ```

     will cause a _SyntaxError_, and result in the following (or similar) message being displayed in the console:

     ```
       File "main.py", line 1

         print("Hello, World!)
                            ^
     SyntaxError: EOL while scanning string literal
     ```

     Pay attention to the arrow – it indicates the place where the Python parser has run into trouble. In our case, it's the missing double quote. Did you notice it?

   - **exceptions**, which occur even when a statement/expression is syntactically correct; these are the errors that are detected during execution when your code results in an error which is not _uncoditionally fatal_. For example: \
     Trying to execute the following line:

     ```python
     print(1/0)
     ```

     will cause a _ZeroDivisionError_ exception, and result in the following (or similar) message being displayed in the console:

     ```
     Traceback (most recent call last):
       File "main.py", line 1, in 
         print(1/0)
     ZeroDivisionError: division by zero
     ```

     Pay attention to the last line of the error message – it actually tells you what happened. There are many different types of exceptions, such as _ZeroDivisionError_, _NameError_, _TypeError_, and many more; and this part of the message informs you of what type of exception has been raised. The preceding lines show you the context in which the exception has occured.

2. You can "catch" and handle exceptions in Python by using the _try-except_ block. So, if you have a suspicion that any particular snippet may raise an exception, you can write the code that will gracefully handle it, and will not interrupt the program. Look at the example:

   ```python
   while True:
       try:
           number = int(input("Enter an integer number: "))
           print(number/2)
           break
       except:
           print("Warning: the value entered is not a valid number. Try again...")
   ```

   The code above asks the user for input until they enter a valid integer number. If the user enters a value that cannot be converted to an int, the program will print `Warning: the value entered is not a valid number. Try again...`, and ask the user to enter a number again. What happens in such a case?

   1. The program enters the _while_ loop.
   2. The `try` block/clause is executed. The user enters a wrong value, for example: `hello!`.
   3. An exception occurs, and the rest of the `try` clause is skipped. The program jumps to the `except` block, executes it, and then continues running after the _try-except_ block.
If the user enters a correct value and no exception occurs, the subsequent instructions in the _try_ block are executed.

3. You can handle multiple exceptions in your code block. Look at the following examples:

   ```python
   while True:
       try:
        number = int(input("Enter an int number: "))
        print(5/number)
        break
    except ValueError:
        print("Wrong value.")
    except ZeroDivisionError:
        print("Sorry. I cannot divide by zero.")
    except:
        print("I don't know what to do...")
   ```

   You can use multiple _except_ blocks within one _try_ statement, and specify particular exception names. If one of the `except` branches is executed, the other branches will be skipped. Remember: you can specify a particular built-in exception only once. Also, don't forget that the **default** (or generic) exception, that is the one with no name specified, should be placed **at the bottom of the branch** (use the more specific exceptions first, and the more general last).

   You can also specify and handle multiple built-in exceptions within a single _except_ clause:

   ```python
   while True:
       try:
           number = int(input("Enter an int number: "))
           print(5/number)
           break
       except (ValueError, ZeroDivisionError):
           print("Wrong value or No division by zero rule broken.")
       except:
           print("Sorry, something went wrong...")
   ```

4. Some of the most useful Python built-in exceptions are: _ZeroDivisionError_, _ValueError_, _TypeError_, _AttributeError_, and _SyntaxError_. One more exception that, in our opinion, deserves your attention is the _KeyboardInterrupt_ exception, which is raised when the user hits the interrupt key (CTRL-C or Delete). Run the code above and hit the key combination to see what happens.

   To learn more about the Python built-in exceptions, consult the official [Python documentation](https://docs.python.org/3/library/exceptions.html#bltin-exceptions).

5. Last but not least, you should remember about testing and debugging your code. Use such debugging techniques as _print_ debugging; if possible – ask someone to read your code and help you to find bugs in it or to improve it; try to isolate the fragment of code that is problematic and susceptible to errors: **test your functions** by applying predictable argument values, and try to **handle** the situations when someone enters wrong values; **comment out** the parts of the code that obscure the issue. Finally, take breaks and come back to your code after some time with a fresh pair of eyes.

**Exercise**

What is the output of the following program if the user enters `0`?

```python
try:
    value = int(input("Enter a value: "))
    print(value/value)
except ValueError:
    print("Bad input...")
except ZeroDivisionError:
    print("Very bad input...")
except:
    print("Booo!")
```

<details>
<summary>Check</summary>

The program will output: `Very bad input....`
</details>
