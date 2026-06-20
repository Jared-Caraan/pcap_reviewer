## Creating your own exceptions

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _exceptions-own_.

Python makes available a few dozen exception types organized into an exception hierarchy, but exceptions are classes like any other. You can use inheritance to create nuances you consider necessary. To do that, all you have to do is put the name of the chosen exception class as the superclass for your own exception. Since Python has so many built in exceptions, it can be difficult to choose which exception should be the superclass for your own exception class. The rule of thumb is if you want to create an exception, that will be a special case of an exception already available in Python, use that one particular Python exception as the superclass. For instance, if you create a function that expects a specific kind of value in one of its parameters and that value is somehow wrong, you can extend the `ValueError` class.

### Sample Usage

<img width="1020" height="668" alt="image" src="https://github.com/user-attachments/assets/4b2f6695-a1b9-4732-951d-a36f4c71454a" /><br>

So here we create an exception class named `AnimalValueError`. Since we want it to be a specific subtype of the `ValueError`, we denote `ValueError` as the superclass for `AnimalValueError`. Note that we do not need to provide any specific content for the new exception type. Everything we need to successfully use this kind of exception will be inherited from the `ValueError` class.

Note that you can pass some arguments to the constructor and the code will work fine. `AnimalValueError` inherits the constructor from the `ValueError` class. That was an example where we created a very specific kind of exception class. But in bigger applications, it may be necessary to create a whole structure of new exception types, in which case it is probably better to inherit from one of the more general exception classes.
<hr>

### Another more specific example
Imagine an application for multiple users where all of the actions are done by specific people. We want to have our own exception classes and we have a very specific requirement. The exceptions should always contain the login of the user that caused the error. We will choose `Exception` - a very general exception class provided by Python as our base class.

<img width="1292" height="511" alt="image" src="https://github.com/user-attachments/assets/16856193-5888-40a4-85a0-85b447935861" /><br>

So here we define `UserActionException`, which inherits directly from `Exception`. We defined a constructor, and this enables the user to provide two very specific arguments - one for the error message, the other one for the ID of the user that was related to this error. You can also see that we override the default `__str__` method so that it returns a meaningful error message alongside the name of the exception class and the user ID.

Now we create a function named `say_hello`. This function expects two arguments - the name of the user that will be used to create the user, and the user ID which will be used in the event of raising an exception. You can now see that when the name is empty, we raise our own custom `UserActionException`. We provide a very custom message which will go into the `message` property and a very custom user ID which will go into the `user_id` property.

In the main part of the code, we use a try-except block when an exception or any of its subclasses such as `UserActionException` is raised, we print the exception object.

Now, of course, we can also create our own exceptional class structure. We can inherit from `UserActionException` to create more specific exception types.

<img width="1152" height="436" alt="image" src="https://github.com/user-attachments/assets/78632519-ec40-4817-b146-0457d66ed688" /><br>

So we created a new exception class: `EmptyNameUserActionException`. It is a specific case of `UserActionException`, which is the superclass for it. The only thing we define in this exception class is the constructor.

We invoke the constructor of the superclass, but we provide a very specific error message. This means that we can now raise `EmptyNameUserActionException`, and we don't need to provide the error message like before because the class itself produces a nice error message. Such an exception type can be useful if you need to raise an exception related to empty names in many places. And of course, depending on your needs, you can create new kinds of exceptions that inherit from `UserActionException`, or even ones that inherit from `EmptyNameUserActionException`.
