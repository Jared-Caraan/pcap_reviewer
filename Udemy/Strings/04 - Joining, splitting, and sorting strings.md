## Joining, splitting, and sorting strings

### `join()`

Let's say that we have the following three strings that we want to join. We want to create a bigger string from these three strings, and we want them to be separated with spaces. To get that, we need to do the following:

<img width="740" height="117" alt="image" src="https://github.com/user-attachments/assets/e7d6c26b-bdcd-408a-873c-41262642c0e6" /><br>
<hr>

### `split()`

It takes a string and splits it into a list of smallest strings. The method assumes that the strings are limited by whitespaces such as the space character or newline characters.

<img width="632" height="90" alt="image" src="https://github.com/user-attachments/assets/177a45cf-44d3-4852-a928-c1b7afd74fe2" /><br>

### Sorting

Generally speaking, Python offers two ways of sorting. The first one is a function named `sorted()`. This function takes a list as its argument and returns a new list with the elements sorted. The original list remains unchanged.

<img width="770" height="158" alt="image" src="https://github.com/user-attachments/assets/da784ab2-97aa-430b-9d2a-c7161562b2aa" /><br>

The second option is to use `sort()`. So it is a bit different because it changes the original list. No new list is created.

<img width="625" height="146" alt="image" src="https://github.com/user-attachments/assets/3534fb52-999e-48cc-8711-f31dc2942be1" /><br>

Which version to choose depends on what you need to achieve. Of course, if you want to create a sorted copy of the original list, use `sorted()`. If you want to change the order of elements in the original list, use `sort()`.


The syntax is therefore also a bit different.
