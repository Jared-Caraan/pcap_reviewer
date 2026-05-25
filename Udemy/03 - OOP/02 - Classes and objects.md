## Classes and objects

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-classes-objects_.

### Classes vs Objects

Classes are templates used to create objects. For example, you can create a class named user. Classes can contain two types of entities - variables called **attributes** and functions called **methods**.

In our simple example, we'll say that each user is characterized by a `username` and a `city`. Each user is also able to introduce themselves. So we will create a method named `introduce`. This class will serve as a template to generate specific users. You could then have a specific user with username _ModernKnight_ from _New York City_. Then you can create another user named _RulerOfDarkness_ from _London_.

<img width="601" height="399" alt="image" src="https://github.com/user-attachments/assets/6d167df7-d251-4e0d-aa19-c055315d66dd" /><br>

These specific users, created on the basis of the user class, are called **objects**. Objects contain the attributes and methods specified in the class, so we know that each user object has a nickname and a city, and we also know that each user object can invoke the introduce method to introduce itself. This is true at the moment when we create an object because later on we can change the properties and methods in the object, but we'll get to that later on.

So that's the main difference between classes and objects. Classes are templates used to create specific objects. We sometimes use the term **instantiate**. We instantiate objects from classes. We can also say that objects are instances of the class. You can't create objects if there is no class, but you can create a class and then never instantiate an object from it. In other words, a class is an idea which can be used to create specific inclinations called objects. Each object has a name, a set of properties and a set of methods.
<hr>

### Syntax

#### class
We always start with the `class` keyword followed by the name of the class and the colon. By convention, class name starts with capital letters. Class names typically only use letters with no digits or special characters like I have here. Each class has its own block of code after the colon. As with any other block of code, you need to use indentation for that. 

#### constructor

Now, as we said before, we want each user object to have a `username` and a `city`. If we want to have that, we need to make use of a special function, a special method inside the user class. This method is generally called **constructor** because it is used to construct objects of a given class. The constructor definition needs to begin in a very specific way. The constructors name is always `__init__`. If you use any other name, Python will not treat that method as a constructor and it will not use it to construct new objects. Just like with any other function in Python, you need to precede the function name with the keyword `def`. After the name you need to provide a pair of parenthesis and provide the arguments. Finally, you need to add a colon.

All Python constructors must have at least one parameter. It is absolutely obligatory for a constructor to have it. You can give it any name that you want, but the convention that you should always follow is `self`. This `self` parameter is always pointing to the object that you are currently creating within the constructor.

We want each object of the user class to have two attributes `username` and a `city`. Remember that attributes are just variables in classes. The way to signify that in Python is as follows. We need to use the `self` argument inside the constructor and provide the name for the attributes after single dots. In general, we use dots in Python objects to refer to the attributes and methods of that object.

<img width="451" height="114" alt="image" src="https://github.com/user-attachments/assets/9e58d21a-35b7-4d89-8841-a6b470742cf9" /><br>

#### method

Now we also mention that each user should be able to introduce themselves. In order to do that, we need to create another function inside the user class. Remember that a function within a class is called a method. This time we are not creating a constructor so we can give the function any name that we want, in this case `introduce`. We use the `self` parameter and again this `self` parameter refers to the current object. Thanks to it we can use `self.nickname` and `self.city` to access the variables or in other words, the properties of the current object.

<img width="719" height="83" alt="image" src="https://github.com/user-attachments/assets/7b6826af-b658-463e-87f0-744183fa89f2" /><br>

#### Final look of a sample class template

<img width="759" height="186" alt="image" src="https://github.com/user-attachments/assets/38f2bf1a-80a2-41a5-b681-a67e639d1a9e" /><br>

#### objects

After the class definition with no indentation will write `sample_user`. This will be our variable and we'll write `User()` with a pair of parenthesis. We created a variable named `sample_user` just like we always do with any other kind of variable. After the assignment operator, however, we do something new, we provide the name of the class followed by a pair of empty parenthesis.

<img width="281" height="71" alt="image" src="https://github.com/user-attachments/assets/ad1f3fa6-346e-423e-b75f-3d5060ab43df" /><br>

Whenever we provide a name of an existing class and we put a pair of parenthesis afterwards, Python knows that it should create a new object from the class. And how does it do that? By calling the constructor. In the constructor, we instructed Python to create two variables inside the object, `nickname` and `city`. We also instructed Python to put some default values for the `nickname` and the `city` - `sampleNickname` and `sampleCity`.

Note one very important thing. Even though the constructor has a parameter called `self`. We do not provide a value for that parameter when creating an object of the class. That first argument of the constructor is filled for us automatically and it will always contain a reference to the object which is being created.

Right now that we have a sample user, one thing that we can do is call it `introduce()` method to see how that works. To do that, we use the same dot notation on the `sample_user` variable. So in order to call a method on an object, we need to provide the variable in which the object is stored. Then we need to use a dot and after that we need to provide the name of the method followed by a pair of parenthesis.

<img width="557" height="85" alt="image" src="https://github.com/user-attachments/assets/d10e3e4e-2dad-4693-97e9-2be380c173f0" /><br>
<hr>

### Setting the attributes

All right, everything looks fine, but our user class is not really sophisticated. In particular, all the users have the same nickname, `sampleNickname` and the same city, `sampleCity`. We would like to provide our own values in the constructor when we create user objects.

So we'll add two parameters in the constructor - `nickname` and `city`. And now, instead of the default values, we'll use the dot notation.

<img width="428" height="107" alt="image" src="https://github.com/user-attachments/assets/49696b01-eb38-403c-9129-6930998d4049" /><br>

Now, you need to provide two argumeents in the `sample_user` object instantation because it doesn't have any default values anymore.

<img width="501" height="191" alt="image" src="https://github.com/user-attachments/assets/7b900acd-6792-4416-a207-56c2e530bebb" /><br>

You can now create more instances of `User` class.

<img width="684" height="276" alt="image" src="https://github.com/user-attachments/assets/055d29c4-f284-4402-b7a6-e5536ad964d9" />
