## `math` module

### methods
Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _modules-math_. Then import the `math` module. We can check what the module contains using the `dir` function that we used before. The `math` module is among the most frequently used ones in Python. It contains a lot of mathematical symbols and functions that you may want to use in your Python programs.

<img width="1693" height="297" alt="image" src="https://github.com/user-attachments/assets/46078f92-3255-40a1-9faa-58df0e488a0f" />

As you can see, there are a lot of entities available here, like, **trigonometric functions** and the **Pi constant**.
<hr>

### Rounding
For the PCAP examination, though, you need to know just six functions from these. We'll start with three similar functions used to **round** numbers. These are `ceil()`, `floor()` and `trunk()`. What's the difference between them? Let's analyze a simple example.

<img width="498" height="247" alt="image" src="https://github.com/user-attachments/assets/97110194-3263-44f9-9d88-2923c587a4b4" />

And when we run the program, you can see four, three and three. So what are the rules?
- When it comes to `ceil()`, it always rounds the number upwards to the nearest integer, never less than the number itself.
  <img width="476" height="337" alt="image" src="https://github.com/user-attachments/assets/4636e513-24e0-4c13-9b55-e135262c0aed" />
  So the first three all return four, because the number four is the nearest integer, not less than these numbers. `ceil(3.0)` returns three because three is not less than `3.0`. So with negative numbers, let's say `-5.4`, you get `-5` because this is the lowest number, not less than the number itself.
- `floor()` is actually the opposite. It always rounds the number downwards to the nearest integer, never greater than the number itself.
  <img width="476" height="331" alt="image" src="https://github.com/user-attachments/assets/c55eabd3-b4bb-43c4-8610-2338b512ec77" />
  These all return three, because the number three is the nearest integer, not greater than these numbers. Then in `floor(-5.4)`, you get `-6`.
- `trunc()` is the easiest function of the three. This function is simply removes the decimal part and returns the integer from the number.
  <img width="495" height="347" alt="image" src="https://github.com/user-attachments/assets/ba3a723e-36ef-40b9-af0e-ecc31662f3fa" />
  And you can see that in each case we simply get the number before the decimal part.

> [!NOTE]
> none of the three functions round the numbers according to the standard mathematical rules of rounding.
<hr>

### Factorial
What is a factorial in maths? It is the multiplication of all positive integers less than or equal to the given number. The factorial for `3` is `3 x 2 x 1`, which is `6`. So now Python can compute that for you using the factorial function.

<img width="508" height="243" alt="image" src="https://github.com/user-attachments/assets/152274a2-68e8-43cc-b864-d65d2171f7a7" />
<hr>

### Square Root
The function simply returns the square root of a given number.
<img width="457" height="189" alt="image" src="https://github.com/user-attachments/assets/75c053bf-18c8-445e-8c4e-b1742b706d2e" />
Note that even though we provide an integer, we get a float in the result.
<hr>

### Hypotenuse
This one has to do with geometry and triangles to be precise. If you have a right angle triangle and you know the length of the two shortest sites, you can use the `hypot()` function to find the longest side, which is also called the **hypotenuse**.
<img width="479" height="142" alt="image" src="https://github.com/user-attachments/assets/2b3cf095-ed97-4ec6-9d69-15e74398102b" />

> [!NOTE]
> Starting from Python 3.8, you can provide more arguments to the `hypot()` function to calculate their so called Euclidean norm.
