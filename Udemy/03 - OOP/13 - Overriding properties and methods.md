## Overriding Properties and Methods

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-property-method-overriding_.

### Method Overriding

We've talked about inheritance and how you can use properties and methods from super classes in subclasses. But imagine the following situation.

We've got a class named `Animal` that will have a simple constructor with `species` property and another method named `produce_sound` that will print a general animal sound and we'll also have a class named `Dog` that will inherit from animal and it will be empty.

<img width="590" height="411" alt="image" src="https://github.com/user-attachments/assets/82f83d61-56a7-4fa5-b42b-d8789cff24d8" /><br>

We've got a general `Animal` class and a more specific `Dog` class. The `Dog` class is empty, but it inherits from the `Animal` class. So when we access the species property on line two, we get the value from the superclass.

But now take a look at the following situation.

<img width="587" height="488" alt="image" src="https://github.com/user-attachments/assets/de3cde56-7493-4db3-9043-ee5fbca934d1" /><br>

And you can see a different output. So we've added some code to the class. Its constructor defines a property named `species` exactly the same property as in the superclass. We also define a method named `produce_sound`, which has the exact same name as the method in the superclass. When we now run the code, you can see that we get a different result. Python shows the property from the `Dog` class and uses the method from the `Dog` class, not from its superclass. This phenomenon is called **method overriding**.

When we define a method with the exact same name in the superclass and the subclass, the method from the subclass overrides in other words, hides the method from the superclass. In general, when you try to access a property or a method in an object, Python will first try to find that entity inside the object itself. If it fails, it then tries to find it in all the classes involved in the object inheritance line from bottom to top with the most general class at the very end. Method overriding helps achieve one of the four core concepts of object oriented programming - **polymorphism**.

<hr>

### Polymorphism

In the most general sense, polymorphism means the ability of classes to take different forms. Usually when we talk about polymorphism, we talk about method overriding.

<img width="457" height="208" alt="image" src="https://github.com/user-attachments/assets/0322f2d5-0a11-4a02-b5d4-1fbfdbaa7149" /><br>

Even though both objects are animals, one of them is more specific and changes the behavior of the superclass, and that's an example of polymorphism. One method name produced sound behaves differentially based on the specific object that calls it.

Another interesting aspect of method overriding and polymorphism is when methods use other methods.

<img width="628" height="707" alt="image" src="https://github.com/user-attachments/assets/a4083e01-81dc-46df-9177-448807923f87" /><br>

So here we have a new method created in the `Animal` class. This method prints a statement and then calls another method `produce_sound`, which prints another statement. In the case of the first pet, which is an instance of the general `Animal` class, the behavior is quite obvious. But note what happens when we invoke the same method from the `Dog` class. The `Dog` class inherits the `present` method from the `Animal` superclass, but when it's time to call the `produce_sound` method, the `Dog` object actually uses its own version of the method. That's because we use the `produce_sound` invocation with the `self` reference, which always points to the current object. As a result, Python always tries to find the matching method within the object itself, and the end result is that even though both objects use the `present` method, they actually behave differentially because behind the scenes they were created using different classes.
