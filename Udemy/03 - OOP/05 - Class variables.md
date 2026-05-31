## Class Variables

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-class-variables_.

### Recap

We have discussed instance variables so far. They are specific to a given object and each object has its own set of instance variables.
<hr>

### Class variables

A class variable is a property that exists in just one copy. It is stored in the class itself. But outside any object, a class variable exists, even if you don't create any object of that class.

<img width="421" height="340" alt="image" src="https://github.com/user-attachments/assets/4c05f753-f10e-4664-83e5-3c2f438f8801" /><br>

We've created a new variable inside the class - `counter`. The aim is to have a variable that will count how many objects of the class were created. Note that this variable is defined in a different way than the `name` and `age` variables. `name` and `age` were defined inside a constructor with the reference to `self`, but the `counter` was defined with no reference to `self` outside the constructor. This makes it a class variable, not an instance variable. Apart from that, when you want to make a reference to a class variable inside the class code, you need to use the class name followed by a dot. We can reference the class variable just like any instance variable using the dot notation. 

<img width="354" height="173" alt="image" src="https://github.com/user-attachments/assets/57c8d218-c703-4c63-b31e-cee715386130" /><br>

But note how this class variable has the same value in all three objects now that we run the code. That's because there's always exactly one copy of a class variable that is shared across all objects.

<img width="478" height="100" alt="image" src="https://github.com/user-attachments/assets/5448779f-7771-49d5-b0f7-4b3ea17b9143" /><br>

What's more, if you try to use the `__dict__`, you will not see the counter class variable. That's because `__dict__` only shows instance variables and ignores class variables.

To see which class variables are available, you need to take a look at the definition of the class itself.

<img width="380" height="178" alt="image" src="https://github.com/user-attachments/assets/73eeec44-0c43-4846-8d4b-2470972cc287" /><br>

But what if you haven't created any objects or you don't have one at hand? You can still access class variables using the class name itself.

<img width="358" height="85" alt="image" src="https://github.com/user-attachments/assets/5740e05f-3d1b-4681-a140-177286b4f944" /><br>
<hr>

### Private class variables

You can also make class variables private, just like with instance variables. The effects will be identical. The name of the class variable will be mangled but still accessible outside the class definition.

<img width="527" height="262" alt="image" src="https://github.com/user-attachments/assets/703e0dab-591f-451b-8592-3bfb1785d75b" /><br>

I've mentioned that you can use the dict variable to see the instance variables for any object created. It turns out that there's also a class variable with the same name.

<img width="1422" height="120" alt="image" src="https://github.com/user-attachments/assets/61de67a9-4283-4753-9c11-8b3aef0e3fab" /><br>

As you can see, the class variable named `__dict__` contains much more data than the instance variable named `__dict__`.
<hr>

### `hasattr()`

You've seen a lot of examples for class variables and instance variables. You also know that we can add or remove properties on the go. As a result, you can never be sure if a given object contains a specific property. One way to check that, of course, is to use the `__dict__` variable. But you can also use a special function named `hasattr()`.

<img width="593" height="362" alt="image" src="https://github.com/user-attachments/assets/aed3d682-a3d6-446c-a3d5-51494978720c" /><br>

The function `hasattr()` accepts two arguments. The first one is the object or a class. The second one is the name of the property.

You can also use the same function to check if a class has a class variable.

<img width="604" height="194" alt="image" src="https://github.com/user-attachments/assets/4a6e3b4f-644c-4693-998f-f9c09a50eb9a" /><br>
<hr>

### `__name__`

Another built in property is `__name__`. It is much less exciting than dict because it only returns the name of the class. What's more, it can only be used with a class name, not with an object name. There is, however, one useful use case. If you combine the `__name__` property with the `type()` function, the `type()` function returns the type of the given variable. It could return something like integer, string, or the class that was used to create an object.

<img width="398" height="117" alt="image" src="https://github.com/user-attachments/assets/7a6e1bc0-7ac7-404b-914d-d5a971274b06" /><br>

So using the combination of `type()` and `__name__`, you can actually output a string which will contain the name of the class used to create the object.
<hr>

### `__module__`

The last built in property worth mentioning is `__module__`. It returns the name of the module that contains the definition of the class. You can use it with both objects and classes, the result will be the same. If the class is defined in the same file, you will instead see `__main__`.

<img width="373" height="99" alt="image" src="https://github.com/user-attachments/assets/28eba697-544b-437d-bdaa-b1e15f6e2297" /><br>
