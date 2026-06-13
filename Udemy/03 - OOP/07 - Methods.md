## Methods

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-methods_.

### Sample Class with Methods (Recap)

<img width="1427" height="842" alt="image" src="https://github.com/user-attachments/assets/15133b80-9eaa-4bed-83fc-bad71222883e" /><br>

Let's do a quick recap. 

A **method** is a function inside a class. Each method must have at least one parameter. This parameter can have any name, but should be named `self` by convention. The `self` parameter identifies the object for which the method is invoked. When you invoke a method outside the class, you should never provide any argument for the `self` parameter. Python will do that automatically for you. If you need some other parameters in your method, you need to place them after the `self` parameter in the function definition. When you invoke such methods, remember that you still need to skip the first `self` parameter.

The `self` parameter in the method definition has a very specific purpose. It allows you to access the properties and other methods of the same object.

One special method in Python's object oriented programming is a **constructor**. A constructor is a method with a special name - `__init__`. The constructor is activated automatically for you whenever you create a new instance i.e., a new object of the given class. You cannot use a return statement in a constructor. A constructor by design is used to return your objects and nothing else and Python will do that automatically
for you. When providing the parameters for a constructor, you can specify default values for all of them.

Methods can be private in the same way that properties can. You need to add a double underscore in front of the methods name. You already know that `__dict__` property that can be used with both objects and class names. When you use it with an object, you will not see the names of any methods. However, you will see them when you use it with the class name.
<hr>

### `__str__`

Now let's take a look at what Python does when we use the print function with an object as an argument.

<img width="607" height="102" alt="image" src="https://github.com/user-attachments/assets/cb0e9493-745a-4a4a-9ec2-996e3f2284e2" /><br>

When you run the code on your computer, you will probably see a different identifier at the end. Don't worry, that's not a problem. It's an internal object identifier used by Python, and it may be different for each object on each machine. In either case, the result of the print statement may not be very helpful if you want to debug your code. Ideally you would like to see some or all of the properties of the object when you use the `print` function. 

Fortunately, you can do that when Python needs a string representation of an object or a class. It calls a method named `__str__`. There is a default implementation of this method and you could see its output on the image above. You can easily override its implementation by adding a new method inside your class.

<img width="762" height="83" alt="image" src="https://github.com/user-attachments/assets/0519ce0d-d81a-4c9e-97fe-6f8aa0e165fe" /><br>

<img width="376" height="90" alt="image" src="https://github.com/user-attachments/assets/7d615591-e964-4afd-b55a-192651057025" /><br>

And now if we run this cell again, you can see that print shows something else. The `__str__` method must have exactly that name, and have exactly one parameter - `self`. It should return a single value. Apart from that, you can put anything that you want in there. You could just return the first name, just the last name, the combination of both or whatever else you need.
<hr>

### Can you have a default value for the self constructor parameter?

The answer is: you can do that, but the value will be simply ignored by Python.

<img width="551" height="192" alt="image" src="https://github.com/user-attachments/assets/5f0bd8a0-a3c7-4c17-b145-cb576a0455e7" /><br>
