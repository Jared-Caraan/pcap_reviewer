## Comparison: Instance, Class, and Local Variables

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _oop-instance-class-local_.

### Recap

Let's do a quick recap with a brand new class. It will be a class named `House`. Each house will have an address, an area and a price.

<img width="1078" height="434" alt="image" src="https://github.com/user-attachments/assets/6455fb98-6944-4b78-a694-d052af515d75" /><br>

So first of all, we create a class variable named `counter`, which is initially equal to zero. Then inside the constructor, we create three instance variables - `address`, `area` and `price`. All of them use the `self` reference so that we know they are instance variables and not class variables. At the very end of this constructor we also increment house counter by one. Note that this one is not an instance variable. It's a class variable because we don't use the `self` reference, instead we use the name of the class. Later on in the code, we've got a methods named `present`. This is a pretty simple method that will present the various information about the House. You can see that it's only references the three instance variables defined in the constructor. Down below, we first create a new house. Then we use the `present` method, and we also print the class variable named `counter` to the output.
<hr>

### Three types of variables

To help you distinguish between three types of variables, we'll use the example of the constructor method.

<img width="518" height="270" alt="image" src="https://github.com/user-attachments/assets/823fc6c1-143c-40ef-a935-3ebfad586971" /><br>

We've used three different assignments - one for `House.quality`, one for `self.quality`, and one for simply `quality`. What's the difference between these three?

- The first one is a class variable. It will belong to the class rather than to the object. Even though we create this variable inside the constructor.
- The second one is an instance variable because it is preceded by the self parameter which points to the current object.
- And the last one is a local variable that exists only in the methods.

But we can print the value of all three variables inside the constructor, and it will work just fine.

<img width="1062" height="591" alt="image" src="https://github.com/user-attachments/assets/c68ee040-2058-4abe-a1b9-e5df5df3143b" /><br>

But what happens outside the class definition?

<img width="432" height="100" alt="image" src="https://github.com/user-attachments/assets/f8ed81db-b146-46b9-9c32-032571122c4d" /><br>

You can see the instance variable printed to the output. There's also a class variable with the same name, but we can't access it using the object `soho_house`. That's because the instance variable overrides the class variable with the same name.

If we do want to see the class variable instead we need to use the class name.

<img width="445" height="134" alt="image" src="https://github.com/user-attachments/assets/e7324abf-b84f-46b4-970b-ce55f4ce9281" /><br>

And finally, how can we see the local variable outside the class?

The answer is we can't. Local variables are only visible within the block where they were created.
