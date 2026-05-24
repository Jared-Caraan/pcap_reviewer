## Introduction to OOP

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-intro_.

We've come to the part of the course where we learn a completely new programming technique, object-oriented programming. It's a very important topic for anyone aspiring to become a professional software developer.
It's also important for anyone else who would like to gain a deeper understanding of programming in Python.

### Procedural Programming
So far, nearly everything we wrote in Python was classified as procedural programming. Procedural programming was a widely used approach to writing code for decades, and it's still in use today in some situations. It is the best choice for many types of projects in general. If you're looking to write a smaller Python program quickly, the procedural approach may be the best choice.

The basic idea behind procedural programming is that we have **procedures**. Procedures in the Python language would be **functions**. Functions simply have a series of steps to be carried out. While you write a program in Python, any function can be invoked at any point. You can even make one function, call another one. Functions in this approach typically work on data, so the whole procedural approach is about calling functions that do something with data.

One of the problems with procedural programming is that there are no restrictions. Any function can call any other function and the functions can work on any data. For instance, someone may provide you with a function that converts temperature degrees from Celsius to Fahrenheit. The function is meant to work on numbers that represent temperature, but if you instead provide the function with a bank account number, it will also work. It's just that the result of this function will not make much sense.
<hr>

### OOP

Object oriented programming tries to eliminate such problems. This programming technique is much younger than procedural programming, but is the de facto standard approach for most big applications nowadays. In object oriented programming, data and functions are enclosed together, forming something called objects. An **object** is a structure that has some data in the form of traits. These traits are called properties, attributes or fields in the world of programming. Objects are also able to invoke some functions in the form of methods. In programs that use object oriented programming, objects interact with each other, exchange data, or call each others' methods.
<hr>

### Example

Suppose that we need a program that asks the user for the width and height of a rectangle. Then the program calculates the area of that rectangle.

In procedural programming, we can do something like this.

<img width="614" height="214" alt="image" src="https://github.com/user-attachments/assets/f4e88873-c85b-4db9-be8a-dc0fedb43099" /><br>

As we said, one of the disadvantages of the procedural approach is that the functions that we define know nothing about the data. We could ask the user for their age and pass that age as the first argument of the function. The function would still work and to produce something that doesn't really make sense. But because the function and the data are not tied together in any way, the function doesn't know that. It just does what it is asked to do.

So in the object approach, this would look something like this.

<img width="521" height="354" alt="image" src="https://github.com/user-attachments/assets/c153841d-83e4-487f-a972-a9950dd918ef" /><br>

All you need to know is that this part of the code is a **class**. A **class** is a template for creating objects of the same type. Our class is named `Rectangle` and it allows us to create rectangle objects.
When we create the objects, we provide the height and the width.

<img width="1375" height="171" alt="image" src="https://github.com/user-attachments/assets/95316eb5-7a03-4e85-9bcc-7db3d031f2bc" /><br>

So here we ask the user to provide a width and height here down below.

<img width="456" height="74" alt="image" src="https://github.com/user-attachments/assets/ba90aa69-d972-4028-8387-f6c0afd9f9ac" /><br>

Then, we create a new rectangle object with the width and the height that we got from the user.

<img width="1370" height="83" alt="image" src="https://github.com/user-attachments/assets/96ad28c3-6f53-4e1c-b0cb-4b80e3ae84fb" /><br>

From this moment on, Python keeps in memory an object, a structure, a rectangle with a specific width and a specific height. The width and the height are tied together. They are no longer two separate variables, like in their procedural approach. Instead, they are kept together.

Of course, you could argue that the procedural approach allows us to keep the width and the height together too. But the difference here with the object is that the object not only has the width and the height, it also has its own function defined within the class - `get_area()`. This function can be used to return the area of this specific rectangle, not any rectangle, but only this specific rectangle that we created. And if we run the program now, we can see that it works in the very same way, but the structure is a bit better.
<hr>

### Philosophy

When you start creating bigger applications, when you start working on the code with other people and you have hundreds or thousands of functions, it's very easy to get lost with bigger applications. People tend to use functions in the wrong way. They either use functions that are not meant to be used at all, or they use functions with the wrong kinds of arguments. The end result is chaos.

Object-oriented approach allows you to organize this case with objects. You clearly define what types of data is used in your application. It is also clearly defined what you can do about the various kinds of data.
