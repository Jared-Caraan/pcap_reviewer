## `random` module

### Python Randomness
You will often read that Python offers pseudo-random number generation. Why pseudo-random and not just random? You would think that it's easy for computers to come up with random numbers, but appearances can be deceptive in this case. Computers can only do things the way you ask them. They can't use imagination to think of a random number. They can only follow an algorithm with some clear predefined steps, and it's difficult to come up with something random when the steps you take are always predefined.

<img width="770" height="409" alt="image" src="https://github.com/user-attachments/assets/87ab2411-7535-4e75-9297-aa33f355a16d" />

The algorithms will typically start with a seed. The **seed** can be treated as a starting value from which Python does some fancy computations to output pseudo-random numbers. If you use the same seed, you will typically always get the same pseudo random numbers. Python can output more than one number based on the same seed.

For example, you could start with a seed of `1` and then get a pseudo-random number of `5` when you first ask for a random number. The second time you ask for a random number, you could get, let's say, `3`. The third time it could be something like `11` and so on. The numbers may seem perfectly random, but if you close your program and start it again, you will again get `5`. Followed by `3` followed by `11`. Not really random anymore, right?

<img width="744" height="327" alt="image" src="https://github.com/user-attachments/assets/cde982e0-9596-4631-acf6-5fada170de9c" />

That's why ideally the seed should also change over time. This way you will get different random numbers if you run your program again later on. And how do you ensure that the seed changes over time? The easiest way is to use time. Python can take the current time and change it into a number that will become the seed for pseudo-random number generation.

<img width="794" height="341" alt="image" src="https://github.com/user-attachments/assets/216804cc-852c-4c62-b3f3-77421ad6cc8d" />

And because the current time is always different, the seed will also be different. As a result, you will get different random numbers.
<hr>

### `random()`

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _modules-random_. Then import the `random` module. The most general function in this module is also called `random()`. It produces a float number between zero and one.

Let's call this function three times in a row and see what we get. You can see that we got three different numbers.

<img width="449" height="264" alt="image" src="https://github.com/user-attachments/assets/ee8e3024-a8cf-45c8-a944-bf43ad9d622d" />
<br>
If we rerun the cells, you can see that the numbers change. That's because by default, Python changes the seed for you, usually based on the local timestamp on your machine.<br>

<img width="447" height="261" alt="image" src="https://github.com/user-attachments/assets/7341093e-32f6-4a07-986e-dd6ef3941596" />
<br>
If for any reason you want to set the seed yourself, you can use the `seed()` function.
<hr>

### `seed()`

And now, before asking for random numbers, we'll set the seat to `0`.

<img width="454" height="285" alt="image" src="https://github.com/user-attachments/assets/73ca04ef-abca-41d2-9fa9-b6757faa35b5" />
<br>
If we rerun the cell, you can see that the pseudo-random values don't change. They are all based on the same seed of `0`. So the series of numbers will receive is always the same.
<hr>

### `choice(), sample()`

Two more functions that you need to know is `choice()` and `sample()`. They are a bit similar because both of them take a sequence as an input. A **sequence** could be a list, a string, and the output is a randomly selected item from the sequence.

And now we have, as you can see, two sample lists, one with integers and one with strings. The `choice()` function works with both of them. It accepts a sequence as the input and outputs a random element from this sequence.

<img width="794" height="239" alt="image" src="https://github.com/user-attachments/assets/84f08484-3ac9-4d90-9b89-d817545a5fd2" />
<br>
Naturally, we can use sequences other than lists. These could be strings or something else. So for example, you can pick a random character from a string using `random.choice()`.

<img width="717" height="104" alt="image" src="https://github.com/user-attachments/assets/43efd557-a100-408f-8a12-a19ab6cc5b7f" />
<br>
But now take a look at the following code where we print ten random elements from the list.

<img width="694" height="435" alt="image" src="https://github.com/user-attachments/assets/2ce9e712-1c4b-4f52-b9b8-26e08418f108" />
