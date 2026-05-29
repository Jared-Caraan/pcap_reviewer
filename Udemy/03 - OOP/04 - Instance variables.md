## Instance variables

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-instance-variables_.

### Sample Class

Here we've got a simple class named `Dog`. In its constructor, we create two properties, `name` and `age`.

<img width="429" height="113" alt="image" src="https://github.com/user-attachments/assets/d100e25e-8b0c-4693-a74a-fd2de406f9e8" /><br>

This kind of property exists when it is created explicitly and is added to an object. One way to do that is during the object's initialization in the constructor as shown in the example. However, once you create an object, Python allows you to add new properties or even remove existing ones.

<img width="368" height="112" alt="image" src="https://github.com/user-attachments/assets/57ddc7c1-5c40-4ebf-8329-770038f89328" /><br>

We have just added a third property to the object `my_pet`. Even though the `Dog` class has only defined two properties for created objects, `name` and `age`, we are able to add a third one using the dot notation.

We are also able to delete any existing property, and now the `my_pet` object only has one of the two properties defined in the constructor - `age`.

<img width="258" height="54" alt="image" src="https://github.com/user-attachments/assets/215e6e5b-e2b9-4d78-8b70-19972ed07024" /><br>

Instead, we have a brand new property that was not defined in the constructor `color`.

All of this has some consequences. First of all, you must be aware that different objects of the same class can have different properties. And second of all, each object has its own set of properties with its own values. The properties of one object don't interfere with the properties of another object in any way. In general, such properties are called **instance variables**.
<hr>

### Instance Variables

An instance is another name for an object - this indicates that instance. Then you may ask - _"If I can dynamically add or delete instance variables of an object, how do I know which instance variables are available in a given object in a given place in the code?"_ Luckily, there's an easy way to check that. Objects created in Python are automatically given a few useful properties and methods. One of them is a dictionary named `__dict__`.

<img width="625" height="353" alt="image" src="https://github.com/user-attachments/assets/87832f58-02b0-4c16-93ac-37e5adafbac7" /><br>

As you can see, the dictionary under the name `__dict__` shows all the currently available properties. You can see how the dictionary changes when we add or delete a property. Keep in mind that you can use the `__dict__` instance variable with any object that you create. Python automatically adds this for you.
<hr>

### Private instance variables

But now let's say that we want to make one of the properties private. In programming, private properties are properties that are not accessible from outside the class.

<img width="524" height="229" alt="image" src="https://github.com/user-attachments/assets/8ee14472-40f4-4b0a-98b9-80fdbe496415" /><br>

When Python sees that you want to add a private property with two underscore signs in front of it, it uses the so called **name mangling**. In other words, you get an additional underscore sign and the class name before the actual name of the private property.

So even though you can use the `__name` inside the class definition, if you try to do that outside the class, you'll get an error. The property is not accessible because there is no such property.

<img width="890" height="342" alt="image" src="https://github.com/user-attachments/assets/500d7662-15b7-41d9-9e29-5e79825814c6" /><br>

But hey, does that mean that you can use that strange name outside the class definition to access the private property? Yes, you can.

<img width="484" height="162" alt="image" src="https://github.com/user-attachments/assets/3ba6edd8-5195-4c7c-b51a-e9a927fb96b2" /><br>

As you can see, making a property private in Python is limited. Someone can still access the property outside the class if they really want to. In the end, we need to treat the double underscore prefix more as a warning. It means that the creator of the class believes you should not modify the given property directly, but formally speaking, there's no way to stop someone from doing it.

Remember one more thing. This name mangling only works if you use the double underscore prefix inside the class. If you try to add a property later in the code outside the class, goat mangling will not work.

<img width="696" height="122" alt="image" src="https://github.com/user-attachments/assets/c9a558dd-4523-4fef-83d8-2aff0169e6a6" /><br>

You can see that this time, name mangling didn't work because we used the double underscore syntax outside the class code.
