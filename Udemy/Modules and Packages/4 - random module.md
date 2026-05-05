## `random` module

### Python Randomness
You will often read that Python offers pseudo-random number generation. Why pseudo-random and not just random? You would think that it's easy for computers to come up with random numbers, but appearances can be deceptive in this case. Computers can only do things the way you ask them. They can't use imagination to think of a random number. They can only follow an algorithm with some clear predefined steps, and it's difficult to come up with something random when the steps you take are always predefined.

<img width="770" height="409" alt="image" src="https://github.com/user-attachments/assets/87ab2411-7535-4e75-9297-aa33f355a16d" />
<br>
The algorithms will typically start with a seed. The **seed** can be treated as a starting value from which Python does some fancy computations to output pseudo-random numbers. If you use the same seed, you will typically always get the same pseudo random numbers. Python can output more than one number based on the same seed.

For example, you could start with a seed of `1` and then get a pseudo-random number of `5` when you first ask for a random number. The second time you ask for a random number, you could get, let's say, `3`. The third time it could be something like `11` and so on. The numbers may seem perfectly random, but if you close your program and start it again, you will again get `5`. Followed by `3` followed by `11`. Not really random anymore, right?

<img width="744" height="327" alt="image" src="https://github.com/user-attachments/assets/cde982e0-9596-4631-acf6-5fada170de9c" />
<br>
That's why ideally the seed should also change over time. This way you will get different random numbers if you run your program again later on. And how do you ensure that the seed changes over time? The easiest way is to use time. Python can take the current time and change it into a number that will become the seed for pseudo-random number generation.

<img width="794" height="341" alt="image" src="https://github.com/user-attachments/assets/216804cc-852c-4c62-b3f3-77421ad6cc8d" />
<br>
And because the current time is always different, the seed will also be different. As a result, you will get different random numbers.
<hr>

### `random()`

The most general function in this module is also called `random()`. It produces a float number between zero and one.
