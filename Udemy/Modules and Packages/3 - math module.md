## `math` module

The notebook for this lesson is named Modules Moth.

The moth module is among the most frequently used ones in Python.

It contains a lot of mathematical symbols and functions that you may want to use in your Python programs.

We can check what the module contains using the dir function that we used before.

So take a look.

First, we'll import math and now we'll do full name in Dear Math Prince the name and at the end put

a tabulator.

All right.

As you can see, there are a lot of entities available here, like, let's say the trigonometric functions.

You can see sine you can see cosine, you can see the pi constant tamba.

For the PCP examination, though, you need to know just six functions from these.

Let's analyze them.

Now.

We'll start with three similar functions used to round numbers.

These are seal, floor and trunk.

What's the difference between them?

Let's analyze a simple example.

So we'll do print math dot seal from, let's say 3.6 and we'll have two similar invocations for.

Floor and full trunk.

And when we run the program, you can see four, three and three.

All right.

So what are the rules?

What's the difference between the three when it comes to seal, it always rounds the number upwards

to the nearest integer, never less than the number itself.

Let's run some tests.

So we'll do print seal and we'll copy paste it a few times to have some experiments here.

So we'll have 3.1 3.505, 3.945 and we'll also have 3.0.

All right.

We forgot about the math prefix.

So the first three all return four, because the number four is the nearest integer, not less than

these numbers.

SEAL 3.0.

Returns three because three is not less than 3.0.

And now let's find out what happens with negative numbers.

So with negative numbers, let's say -5.4, you get minus five because this is the lowest number, not

less than the number itself.

Four is actually the opposite.

It's always rounds the number downwards to the nearest integer, never greater than the number itself.

So let's do similar tests now.

But instead of using seal, we'll use flow.

Let's copy paste that and let's see what we have.

All right.

These all return three, because the number three is the nearest integer, not greater than these numbers.

For 3.0, it's again three.

It's not greater than this number and four -5.4.

You get minus six.

If we go to minus five, that would break the definition because minus five is actually greater than

-5.4.

And finally, trunk, trunk is the easiest function of the three.

This function is simply removes the decimal part and returns the integer from the number.

Let's find it out.

So instead of law, we'll have a trunk here.

And you can see that in each case we simply get the number before the decimal part.

On a side note, none of the three functions round the numbers according to the standard mathematical

rules of rounding.

You can use the round function, but it's not required for the examination.

You also need to know the factorial function.

What is a factorial in maths?

It is the multiplication of all positive integers less than or equal to the given number.

So I have some examples here.

The factorial for three is three times two times one, which is six.

And now another example, the factorial of four is four times three times two times one, which is 24.

So now Python can compute that for you using the factorial function.

Let's say print math, factorial of three, which is six.

And if we do that for four, you get 24.

All right.

The next function that you need to know is Askew Art, which stands for the square root.

As the name suggests, the function simply returns the square root of a given number.

So, for example, print math asked of 16 would give us 4.0 because four times four is 16.

And now the square root of I don't know, 100 would be ten because ten times ten is 100.

Note that even though we provide an integer, we get a float in the result.

Finally, you need to know the high port function.

This one has to do with geometry and triangles to be precise.

If you have a right angle triangle and you know the length of the two shortest sites, you can use the

high function to find the longest side, which is also called the hypotenuse.

So for let's say, hi port three and four, you will get five and so on.

Starting from Python 3.8, you can provide more arguments to the hybrid function to calculate their

so called Euclidean norm.

This usage is however quite rare, so you do need to worry about it too much.

And that's it.

Python's math module has much more to offer, but these six functions are everything you need to know

for the AP exam.
