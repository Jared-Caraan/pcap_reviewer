### Objectives

Familiarize the student with:

- using the if-else instruction to branch the control path;
- building a complete program that solves simple real-life problems.

### Scenario

Once upon a time there was a land - a land of milk and honey, inhabited by happy and prosperous people. The people paid taxes, of course - their happiness had limits. The most important tax, called the _Personal Income Tax_ (_PIT_ for short) had to be paid once a year, and was evaluated using the following rule:

- if the citizen's income was not higher than 85,528 thalers, the tax was equal to 18% of the income minus 556 thalers and 2 cents (this was the so-called _tax relief_)
- if the income was higher than this amount, the tax was equal to 14,839 thalers and 2 cents, plus 32% of the surplus over 85,528 thalers.

Your task is to write a **tax calculator**.

- It should accept one floating-point value: the income.
- Next, it should print the calculated tax, rounded to full thalers. There's a function named `round()` which will do the rounding for you - you'll find it in the skeleton code in the editor.

> [!NOTE]
> this happy country never returns money to its citizens. If the calculated tax is less than zero, it only means no tax at all (the tax is equal to zero). Take this into consideration during your calculations.

Look at the code in the editor - it only reads one input value and outputs a result, so you need to complete it with some smart calculations.

Test your code using the data we've provided.

### Test Data

Sample input: `10000`

Expected output: `The tax is: 1244.0 thalers`
<hr>

Sample input: `100000`

Expected output: `The tax is: 19470.0 thalers`
<hr>

Sample input: `1000`

Expected output: `The tax is: 0.0 thalers`
<hr>

Sample input: `-100`

Expected output: `The tax is: 0.0 thalers`
<hr>

### Solution

<details>
<summary>Check</summary>

```python
income = float(input("Enter the annual income: "))

if income <= 85_528.0:
    tax = (income * 0.18) - 556.02
else:
    tax = 14_839.02 + ((income - 85_528.0) * 0.32)

if tax <= 0:
    tax = 0.0

tax = round(tax, 0)
print("The tax is:", tax, "thalers")
```

**Output:**
```
Enter the annual income: 10000
The tax is: 1244.0 thalers
Enter the annual income: 100000
The tax is: 19470.0 thalers
Enter the annual income: 1000
The tax is: 0.0 thalers
Enter the annual income: -100
The tax is: 0.0 thalers
```
</details>
