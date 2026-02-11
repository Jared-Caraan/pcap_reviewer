### Objectives

- becoming familiar with the inputting and outputting of data in Python;
- evaluating simple expressions.

### Scenario

Your task is to complete the code in order to evaluate the results of four basic arithmetic operations.

```python
# input a float value for variable a here
# input a float value for variable b here

# output the result of addition here
# output the result of subtraction here
# output the result of multiplication here
# output the result of division here

print("\nThat's all, folks!")
```

The results have to be printed to the console.

You may not be able to protect the code from a user who wants to divide by zero. That's okay, don't worry about it for now.

Test your code - does it produce the results you expect?

We won't show you any test data - that would be too simple.

<details>
<summary>Check Answer</summary>

```python
# input a float value for variable a here
a = input("enter first float: ")
# input a float value for variable b here
b = input("enter second float: ")
# output the result of addition here
print("Sum: " + str(float(a) + float(b)))
# output the result of subtraction here
print("Difference: " + str(float(a) - float(b)))
# output the result of multiplication here
print("Product: " + str(float(a) * float(b)))
# output the result of division here
print("Quotient: " + str(float(a) / float(b)))

print("\nThat's all, folks!")
```

Output:
```
enter first float: -23.699
enter second float: 45.633
Sum: 21.934
Difference: -69.33200000000001
Product: -1081.4564670000002
Quotient: -0.5193390747923652

That's all, folks!
```
</details>
