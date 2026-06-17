## Multiple Inheritance

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-multiple-inheritance_.

### Definition

In a nutshell, it's a situation when a class has more than one super class. In other words, it's a situation in which a class inherits from more than one class. Syntax-wise, using multiple inheritance is quite simple. All you have to do is provide all the subclasses separated by commas. The difficulty about multiple inheritance is elsewhere. It is very easy to lose track of what properties or methods are inherited.
<hr>

### Implementation

<img width="500" height="431" alt="image" src="https://github.com/user-attachments/assets/4317a039-e01f-4867-83a2-2c4f0fec3f9b" /><br>

`Airplane` inherited the methods from both classes, and that's the basis of multiple inheritance.

<img width="497" height="517" alt="image" src="https://github.com/user-attachments/assets/efac4722-4a96-40c2-98c2-3dea2a6603c8" /><br>

Why was the `Vehicle` method version chosen over the `Flyable` method version? The answer is something called **MRO** or **Method Resolution Order**. MRO explains how a given programming language tries to find the method that is currently needed. Each programming language has a slightly different MRO.
<hr>

### Python's MRO

<img width="986" height="432" alt="image" src="https://github.com/user-attachments/assets/8bc8d0e3-5df7-4ef8-8274-82e29035c59c" /><br>

You can see that `Vehicle` was defined as the first superclass of `Airplane`, which is why `Vehicle`'s version of `introduce` was preferred.

Now let's do a small experiment and change the order of super classes for airplane.

<img width="492" height="510" alt="image" src="https://github.com/user-attachments/assets/3224cbc7-a3a5-4bab-8614-bf530ab8e31a" /><br>

That's because `Flyable` is now the first superclass defined in front of the `Vehicle`.

<img width="517" height="542" alt="image" src="https://github.com/user-attachments/assets/ac0deac7-29f5-4d96-abc7-4df5025f3ccf" /><br>

So this time you can see that the `Airplane` object did not use the `introduce` method from `Vehicle` or `Flyable`. Instead it used its own version.
