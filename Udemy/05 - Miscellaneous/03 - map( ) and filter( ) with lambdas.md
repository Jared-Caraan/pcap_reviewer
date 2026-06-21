## map() and filter() with lambdas

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-map-filter_.

### `map()`

`map` typically takes two arguments - the first one is a function, the second one is a sequence with some elements. Then `map` applies the function to all the elements in the sequence. Instead of printing to the output the result of each invocation, it creates a structure called an **iterator**.

<img width="661" height="298" alt="image" src="https://github.com/user-attachments/assets/cc012d7c-ac5f-4137-8b57-833cf6ec8b2e" /><br>

<img width="615" height="143" alt="image" src="https://github.com/user-attachments/assets/0d158e97-c348-4566-9cd6-bece22ee50a6" /><br>

<img width="660" height="120" alt="image" src="https://github.com/user-attachments/assets/b742a1be-83ba-44f5-9822-64d3485888eb" /><br>

Believe it or not, we can reduce all of this code into a single line like this.

<img width="675" height="102" alt="image" src="https://github.com/user-attachments/assets/32b13c7e-e4fd-486d-86f9-2b744db7b9c9" /><br>
<hr>

### `filter()`

`filter` works in a similar way to `map`. It also accepts a function and a sequence. It also returns an iterator. The difference between `map` and `filter` is that `filter` uses the function to well, as the name suggests, to filter the elements of the sequence.

<img width="846" height="102" alt="image" src="https://github.com/user-attachments/assets/bef5ef89-d341-4fea-bdf0-f6d8b672b733" /><br>

So we have a list of numbers from 1 to 8. We would like to have a new list that only contains even numbers. To do that we make use of the `filter` function here. The lambda in this case contains the condition that each matching elements should satisfy. And just as the function name suggests, we successfully filtered out all odd numbers and only got even numbers in the resulting list.

Let's do one more example with filter. We will provide a list of email addresses and we will filter out those that are fake. That is, they don't contain the _@_ sign.

<img width="902" height="277" alt="image" src="https://github.com/user-attachments/assets/f2225f36-c126-4bb3-9fa6-426dc1e45492" /><br>

As you can see, thanks to lambda, we only needed a single line to get a new list with correct email addresses.
