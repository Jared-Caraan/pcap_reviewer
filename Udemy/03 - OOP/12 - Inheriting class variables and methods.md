## Inheriting Class Variables and Methods

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-inheritance-properties_.

### Inheriting class variables

You can start with the three created classes from the previous session.

<img width="610" height="281" alt="image" src="https://github.com/user-attachments/assets/423bfc4d-20d5-4e63-b30e-f94a1fe1cb75" /><br>

We already know how instance variables can be inherited using constructors, but how about class variables? It turns out that they work exactly the same way, and it turns out that you can use the same syntax to get them.

<img width="832" height="436" alt="image" src="https://github.com/user-attachments/assets/67a8cd81-6699-4e53-92a2-9211506f14db" /><br>

So here, we defined a class variable in the `Vehicle` class and we could then easily access this variable in the subclass using the dot notation with the superclass name. And again we can use the notation with the class name or we can use the `super` keyword.

<img width="845" height="423" alt="image" src="https://github.com/user-attachments/assets/c7443cce-8651-434e-a027-ee7e52985ef5" /><br>

Outside the class definition, we can easily access the class variable from vehicle using the dot notation.

<img width="582" height="112" alt="image" src="https://github.com/user-attachments/assets/fd7e52ec-372b-4500-bb4b-ab4a283b2717" /><br>

<hr>

### Inheriting methods

<img width="812" height="712" alt="image" src="https://github.com/user-attachments/assets/200dfe76-1050-4929-8d3c-dfd7f5c73752" /><br>

Look how we added a `speed_up` method in the `LandVehicle` superclass. Then in the `Car` subclass we created a `super_speed` method where we invoke this method three times in a row. Again, we can use the super keyword or we can use the class name.

If we don't want to speed up so aggressively with our `my_car` object, we can of course also use the `speed_up` method directly.

<img width="562" height="312" alt="image" src="https://github.com/user-attachments/assets/23de7e07-1200-4550-a11e-50535ada6090" /><br>
