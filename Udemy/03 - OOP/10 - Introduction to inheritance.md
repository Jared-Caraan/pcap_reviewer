## Introduction to inheritance

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-inheritance-intro_.

### Definition

Inheritance is a mechanism where one object or class is based on another object or class. This way we can create super classes which are broader and more general, as well as subclasses which are detailed and concrete.

A common example would be vehicles.

<img width="772" height="341" alt="image" src="https://github.com/user-attachments/assets/6f0f2594-5b87-49f8-91a1-cac33529a986" /><br>

You could have a general class named vehicle, and you could then create more specific classes - a land vehicle or a water vehicle. And then again, a land vehicle could be a car or a motorcycle. A water vehicle, for instance, could be a boat. In this hierarchy, we start with the broadest class definition - vehicle. Each land vehicle is a vehicle. Each water vehicle is also a vehicle. And finally, a car, a motorcycle, and a boat. They are also all vehicles. In this setup, we can say that, for instance, land vehicle is a super class of car. Vehicle is also a super class of car, and car is a subclass of land vehicle.
<hr>

### Implementation

<img width="462" height="247" alt="image" src="https://github.com/user-attachments/assets/1b80f55a-8f57-401a-8267-4fed15c4c8bf" /><br>

Note that `LandVehicle` has a pair of brackets after its name. In the brackets we provide the name of the superclass, which is `Vehicle`. The same goes for `Car` in the brackets. We provide the name of the `LandVehicle`. This way `Car` has become a subclass of `LandVehicle` and `LandVehicle` has become a subclass of `Vehicle`. We can check that using python's `issubclass()` function.

<img width="465" height="83" alt="image" src="https://github.com/user-attachments/assets/5f6aa6f9-cfbd-4a76-ad56-a7227664d606" /><br>

The class that we test does not need to be an immediate subclass of the other class. In our case, a `Car` is also a subclass of `Vehicle`, even though not directly. 

<img width="427" height="83" alt="image" src="https://github.com/user-attachments/assets/c07e3541-a95a-4681-aaa3-a324af88f65a" /><br>

Interestingly, a `Car` is also always a subclass of itself.

<img width="375" height="87" alt="image" src="https://github.com/user-attachments/assets/f5714d0d-56b2-4f2a-ba8f-a2691e3df96c" /><br>
