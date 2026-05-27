## Encapsulation and Abstraction

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-encapsulation-abstraction_.

### Sample Class and Object

All right, let's create a new simple class now. The class will be called `Car`. It will be a very simple class that describes a very generic car. It will have three properties - `model`, `color`, and car `speed`.

<img width="611" height="137" alt="image" src="https://github.com/user-attachments/assets/8af5be81-beae-432e-bb58-0dff04779210" /><br>

So let's run the cell and now we'll create a new object.

<img width="476" height="64" alt="image" src="https://github.com/user-attachments/assets/06087776-eca5-4239-a2e9-bbdbb5b81a6f" /><br>

And when you run the code, you can see that everything works fine.
<hr>

### Putting values here and there

Now do you remember how to provide default values for function parameters? Turns out that it works with constructor and other methods within classes too.

<img width="669" height="136" alt="image" src="https://github.com/user-attachments/assets/b4cce345-c1e8-4c7c-9be4-ee2b06ca8c90" /><br>

And now every car that is created without providing an initial speed will be given the default value of zero. So now it's possible to create a new car using one argument less and Python will fill that automatically for us.

<img width="441" height="50" alt="image" src="https://github.com/user-attachments/assets/271e6626-aa8d-4ebb-ad4c-5c8894046330" /><br>

We'll add two new methods to the class that will make the class speed up or slow down.

<img width="617" height="267" alt="image" src="https://github.com/user-attachments/assets/2cf9c513-dbe2-4736-a696-2b562672ad21" /><br>

And remember that each method in your class should contain a single parameter at least, which is by convention named `self`. This argument allows you to access the object's properties and increase or decrease the speed by five.

All right, we'll add one more method that will present the current speed to the user.

<img width="448" height="64" alt="image" src="https://github.com/user-attachments/assets/86fc109c-1b05-4e88-9a3c-87622fe999a5" /><br>

<img width="472" height="164" alt="image" src="https://github.com/user-attachments/assets/1666a5a2-c902-4285-9ab3-0422b42cf919" /><br>

But now there is one problem. If the current speed is zero, it shouldn't be possible to slow down.

<img width="514" height="160" alt="image" src="https://github.com/user-attachments/assets/79cb09cf-0f0d-4366-9773-2395e95e4878" /><br>

A speed of minus ten doesn't really make much sense. We should modify our code so that it doesn't decrease the speed below zero.

<img width="580" height="389" alt="image" src="https://github.com/user-attachments/assets/323d0df7-3965-4ff9-aa40-968deeb9e7e3" /><br>

But there's one more problem. What happens if the user provides a value below zero when they create a car?

<img width="601" height="113" alt="image" src="https://github.com/user-attachments/assets/57bb3ddf-1ac0-42c1-b875-d6880f658393" /><br>

And now if we try to show the speed without slowing down or speeding up, you can see the value of `-50`. Well, that doesn't make much sense either. We need to also modify our constructor so that it doesn't allow speed values below zero.

<img width="604" height="195" alt="image" src="https://github.com/user-attachments/assets/cfb0aedd-b292-49ad-84a5-6d3a60cbf94d" /><br>

Our class is now almost bulletproof in terms of speed, but unfortunately, there's one more way that the user may try to hack our class.

<img width="572" height="136" alt="image" src="https://github.com/user-attachments/assets/c7ac14e1-e159-481c-8b74-abaf58eb52a6" /><br>

As you can see, the user can simply access the `speed` property directly using the dot notation and set any `speed` value that they want. What can we do about it? The user does not call any method defined in the clause, so there is no place where we could add some checks for speeds below zero.

Luckily, there is a way to kind of stop the user from changing the speech property directly. We need to make the property **private**.
<hr>

### Private property

A **private** property is a property that can only be accessed from within the class. In one of the methods, but never outside the class after the object is created. So in the properties private, you can't do an operation like the one above.

Different programming languages implement the concept of private properties differentially. In Python, if you want a private property, you need to give it a name that starts with two underscore signs.

<img width="759" height="616" alt="image" src="https://github.com/user-attachments/assets/5f91198b-216a-4660-8a22-1569f5eb33b1" /><br>
<hr>

### OOP Principles

Incidentally, there are four main principles behind object oriented programming in most modern programming languages:

1. encapsulation
2. abstraction
3. inheritance
4. polymorphism

In this video, the usage of private properties mainly addresses the concept of **encapsulation**. Encapsulation says that objects should keep their state private and only expose a set of public functions to the outside world. This is exactly what we did here. We made the `speed` property private, so we hid the state of the object from the outside world and we exposed two methods `speed_up` and `slow_down` to manipulate the property in a way we previously defined. This also shows the second principle behind object oriented programming - **abstraction**.

Abstraction says that objects should keep the details of how they work to themselves and only expose some high level operations to the outside world. Theoretically speaking, if someone uses your car class, they don't even need to know that there is a `speed` property in sight. They can create a car object without providing any speed, and then they can only use the `speed_up` and `slow_down` methods. The details of what happens inside the object when you call these methods are abstracted away from you.
