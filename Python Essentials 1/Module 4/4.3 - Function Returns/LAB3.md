### Objectives

Familiarize the student with:

- projecting and writing parameterized functions;
- utilizing the `return` statement;
- building a set of utility functions;
- utilizing the student's own functions.

### Scenario

Your task is to write and test a function which takes three arguments (a year, a month, and a day of the month) and returns the corresponding day of the year, or returns `None` if any of the arguments is invalid.

Use the previously written and tested functions. Add some test cases to the code. This test is only a beginning.

```python
def is_year_leap(year):
#
# Your code from LAB 4.3.1.6.
#

def days_in_month(year, month):
#
# Your code from LAB 4.3.1.7.
#

def day_of_year(year, month, day):
#
# Write your new code here.
#

print(day_of_year(2000, 12, 31))
```

### Solution

<details>
<summary>Check</summary>

```python
def is_year_leap(year):
    if (year % 4 == 0 and year % 100 != 0) or (year % 400 == 0):
        return True
    return False

def days_in_month(year, month):
    if year < 1 or month < 1 or month > 12:
        return None
    days = [31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31]
    if month == 2 and is_year_leap(year):
        return 29
    return days[month - 1]

def day_of_year(year, month, day):
    days_in_target_month = days_in_month(year, month)
    if days_in_target_month is None or day < 1 or day > days_in_target_month:
        return None
    
    total_days = day
    for m in range(1, month):
        total_days += days_in_month(year, m)
    
    return total_days

print(day_of_year(2000, 12, 31))
```
</details>
