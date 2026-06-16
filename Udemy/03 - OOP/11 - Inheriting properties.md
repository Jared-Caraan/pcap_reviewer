## Inheriting properties

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-inheritance-properties_.

### Inheritance implementation

Let's add content to the three classes to see how inheritance really works.

<img width="405" height="210" alt="image" src="https://github.com/user-attachments/assets/0c64a661-e64c-4aec-97ab-a79c471d33e7" /><br>

The classes don't have any constructors defined, they don't contain any properties. And so you can see that we create a `Car` with no arguments passed in the brackets. When you check the `__dict__` property for the object created, it is empty. No properties, no methods, nothing.

<img width="402" height="120" alt="image" src="https://github.com/user-attachments/assets/7d789b34-8503-4af9-b521-f506e89f58eb" /><br>

Now let's add a constructor to the top hierarchy vehicle class.

<img width="902" height="492" alt="image" src="https://github.com/user-attachments/assets/a2101183-3898-4e39-a179-470de04f647a" /><br>

And now when you want to run the code, it fails. The constructor is missing one required positional argument named `speed`. How is that possible? We don't have any constructor or any property defined in the `Car` class. The answer is quite simple. If we don't define a constructor for `Car` explicitly, Python will try to look for a constructor in all of these super classes. There's no constructor in `LandVehicle`, but there is one in `Vehicle`, so Python will use that constructor for creating `Car`. All of this happens because `Car` inherits from `LandVehicle` which in turns inherits from `Vehicle`. All the properties and methods defined in `Vehicle` will therefore be visible in `Car`. 

This means that we now need to provide an argument for the `speed` parameter in the `Car` subclass.

<img width="497" height="366" alt="image" src="https://github.com/user-attachments/assets/8fc7ab47-3391-47ce-a3b1-cd638cfefde8" /><br>

As you can see, `Car` inherited the `speed` property from the `Vehicle` superclass.

Now what happens when we create a constructor in the `LandVehicle` in turn?

<img width="580" height="377" alt="image" src="https://github.com/user-attachments/assets/b4cfb63e-17e4-49e9-89c5-e58ad9e80f55" /><br>

We could successfully create an object of class `Car`, but the `speed` property from the `Vehicle` constructor is gone. How is it possible?

The rule is that Python only inherits the constructor from the superclass if there is no constructor defined in the given class. In the previous example, `Car` didn't have a constructor, so it inherited a constructor from `LandVehicle` and because `LandVehicle` did not have a constructor either, it inherited the constructor defined in the `Vehicle` class. As a result, the constructor from `Vehicle` was used to create a `Car` object.

And here when we defined a constructor in `LandVehicle`, it did not inherit the one for a `Vehicle`. That means that `LandVehicle` has its own constructor now, which is not related to the `Vehicle` constructor in any way. And this time `Car` inherited this new constructor from `LandVehicle` which doesn't have a `speed` property.

It looks like `Car` only has the properties from their `LandVehicle`, but it doesn't have the property from `Vehicle`. How to change that? All we need to do is invoke the `Vehicle` constructor from the `LandVehicle` constructor directly.

<img width="657" height="388" alt="image" src="https://github.com/user-attachments/assets/3c903a84-b016-4e5e-96e8-0b2d79cce900" /><br>

So in short, to invoke the constructor from the superclass, we can use the dot notation with the name of the superclass, but we can also do something else.
<hr>

### `super`

Instead of `Vehicle`, we're going to use `super()` and get rid of `self`.

<img width="1528" height="427" alt="image" src="https://github.com/user-attachments/assets/de6f6c1d-70b2-4049-a74b-a5b0a68190ed" /><br>

Note a subtle difference when we use the `super()` keyword instead of the superclass name, we don't need to provide the `self` parameter. It will be automatically passed for us by Python to a superclass constructor. Both notations, the one with the class name and the one with the `super` keyword allow you to use constructors from super classes. This in turn means that we can inherit instance variables from super classes outside the class definition.

<img width="370" height="137" alt="image" src="https://github.com/user-attachments/assets/8911929d-62d4-4076-b2c2-084291df3931" /><br>
