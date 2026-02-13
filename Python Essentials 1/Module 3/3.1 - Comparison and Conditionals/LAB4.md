### Objectives

Familiarize the student with:

- using the `if-elif-else` statement;
- finding the proper implementation of verbally defined rules;
- testing code using sample input and output.

### Scenario

As you surely know, due to some astronomical reasons, years may be _leap_ or _common_. The former are 366 days long, while the latter are 365 days long.

Since the introduction of the Gregorian calendar (in 1582), the following rule is used to determine the kind of year:

if the year number isn't divisible by four, it's a _common_ year;
otherwise, if the year number isn't divisible by 100, it's a _leap_ year;
otherwise, if the year number isn't divisible by 400, it's a _common_ year;
otherwise, it's a _leap_ year.

Look at the code in the editor - it only reads a year number, and needs to be completed with the instructions implementing the test we've just described.

The code should output one of two possible messages, which are `Leap year` or `Common year`, depending on the value entered.

It would be good to verify if the entered year falls into the Gregorian era, and output a warning otherwise: `Not within the Gregorian calendar period`. Tip: use the `!=` and `%` operators.

Test your code using the data we've provided.

### Test Data

Sample input: `2000`

Expected output: `Leap year`
<hr>

Sample input: `2015`

Expected output: `Common year`
<hr>

Sample input: `1999`

Expected output: `Common year`
<hr>

Sample input: `1996`

Expected output: `Leap year`
<hr>

Sample input: `1580`

Expected output: `Not within the Gregorian calendar period`

### Solution

<details>
<summary>Check</summary>

```python
year = int(input("Enter a year: "))

if year % 4 != 0:
    text = "Common year"
elif year % 100 != 0:
    text = "Leap year"
elif year % 400 != 0:
    text = "Common year"
else:
    text = "Leap year"

if year < 1582:
    print("Not within the Gregorian calendar period")
else:
    print(text)
```

**Output:**
```
Enter a year: 2000
Leap year
Enter a year: 2015
Common year
Enter a year: 1999
Common year
Enter a year: 1996
Leap year
Enter a year: 1580
Not within the Gregorian calendar period
```
</details>
