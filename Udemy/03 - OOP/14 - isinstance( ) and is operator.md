## `isinstance()` and `is` operator

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-isintance-is_.

### `isinstance()`

All of these subclasses and invoking constructors from super classes that we already discussed may be a bit confusing. If at any point you're in doubt as to which class was used to instantiate a given object, you can always use a method named `isinstance()`.

<img width="687" height="667" alt="image" src="https://github.com/user-attachments/assets/f1e2f734-fc8f-4b95-a51a-d17ed93c23d0" /><br>

So looking at it, `isinstance()` a returns `true` if an object was created with a given class, but it also returns `true` if the object was created from a subclass of the class that we provide.
<hr>

### `is` operator for OOP

There's also an operator that you can use with two object variables - `is`. The operator checks whether two variables point to the same object. How does that work?

Remember that variables don't store objects directly. Variables actually store references to objects in the memory. In other words, object variables contain the address of an object in the memory, not the object itself, and this has some consequences.

<img width="433" height="72" alt="image" src="https://github.com/user-attachments/assets/9feee9d9-862b-4a6f-bdd8-5cd9c969d82b" /><br>

The first line creates a new object. We can be sure of that because we can see the name of the class followed by a pair of brackets. On line two, we assign the value of `my_vehicle` to a new variable, `my_new_vehicle`. Because `my_vehicle` only stores the reference to the actual object, `my_new_vehicle` gets that reference and both variables point to the same object. You can easily check that using the `is` operator.

<img width="535" height="95" alt="image" src="https://github.com/user-attachments/assets/ea48fb2e-39ac-4a2f-9780-05762efcedae" /><br>

This approach has some consequences. If you make any changes to the object using one of the variables, that change will be visible in the second variable as well.

<img width="711" height="150" alt="image" src="https://github.com/user-attachments/assets/89f268a2-76a4-4e6e-a8cf-ec1cd637f9c3" /><br>

As you can see, the change applied to the `my_vehicle` object is also visible to the `my_new_vehicle` object because they both reference the very same object in their memory.

If you want to have two different objects, you need to use dot notation with class name plus parenthesis.

<img width="731" height="252" alt="image" src="https://github.com/user-attachments/assets/7a0ea7ba-669d-4b18-b20d-594017485341" /><br>

You will now see that the change to the speed in `my_vehicle` to `30` is completely independent of the `speed` in the `my_new_vehicle` object reference.
<hr>

### `is` operator outside OOP

#### integers

<img width="497" height="132" alt="image" src="https://github.com/user-attachments/assets/f5cbae31-6bd7-4fda-809f-cc609bf011cd" /><br>

If two variables contain the very same integer number, the result of using the `is` operator is `true`.

<img width="497" height="180" alt="image" src="https://github.com/user-attachments/assets/10580b5c-da1c-4bcc-bb17-0143afd72870" /><br>

The `is` operator still returns `true` as you can see.

#### strings

<img width="480" height="132" alt="image" src="https://github.com/user-attachments/assets/c4529e0c-b8af-433c-a435-8a235a61a890" /><br>

However, you need to remember that strings are immutable. If you try to change an existing string, python will instead create a new one.

<img width="542" height="166" alt="image" src="https://github.com/user-attachments/assets/f0a19465-b377-4ad3-8428-6309f1d870ac" /><br>

So at first sight, this example looks similar to the one with integers. However, something different happens. The second string is initially different from the first one, but on line three we add the missing `O` at the end of the string. The strings now seem identical, but the `is` operator returns false. That's because whenever we try to modify an existing string, python instead creates a new one, even though `first_str` and `second_str` contain identical strings, they are actually two separate objects in the memory. That's where the _equality_ operator gives a different result.

 <img width="475" height="191" alt="image" src="https://github.com/user-attachments/assets/5c54a8b4-a204-4cd4-bd75-cefd805bcc66" /><br>

The equality operator returns true because both variables contain the very same string value, but because the actual string objects behind them are two different objects in the memory that `is` operator returns false.
