## `platform` module

### Preface
Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _modules-platform_. The last standard Python module that you need to know for the PCAP examination is called **platform**. The documentation describes it as "access to underlying platforms identifying data". In other words, the platform module can tell you a little bit about your Python version, the operating system, and the hardware you're using.

Take a look at the diagram. It shows the layers between your code and the hardware that your computer is using. Your code is located at the very top level. Below, is the running environment of Python. The next layer is the operating system. Python uses a lot of helpers from the operating system for things such as processing files or communicating with physical devices. At the very bottom, there's the hardware, the processor, the RAM memory, network interfaces, user keyboard and mice, and others. All of the four layers cooperate so we can write Python programs.

<img width="656" height="370" alt="image" src="https://github.com/user-attachments/assets/caddc0cf-40f6-4c2f-8201-277920d21b88" /><br>

For example, when you want to get some user data, your code can invoke the `input()` function. The Python environment accepts the order and adapted to meet the requirements of the local operating system.

### `platform()`

First of all, we'll import the module and now we'll start with `platform()`. This function returns a string that identifies the underlying platform. The input is intended to be human readable. As you can see here, the platform that I'm using is Windows ten with this specific version.

<img width="506" height="180" alt="image" src="https://github.com/user-attachments/assets/d28a4aa0-0513-4eb3-8455-e993b681408d" /><br>

The function actually takes two parameters that have some default values, that's why I didn't have to provide any arguments. 
- When `aliased` is set to `True` or any non-zero value, the function may present alternative underlying names. This parameter will not do anything on certain platforms while on others it can show system names that differ from common names.
- When `terse` is set to `True` in turn or any non-zero value, the function will try to present a briefer form if any such form is available.

<img width="777" height="72" alt="image" src="https://github.com/user-attachments/assets/796a022e-191d-428e-bec2-7b3ab27f8958" /> <br>

So for instance, if I set both of these to true, you can see a brief form Windows ten.

<img width="538" height="100" alt="image" src="https://github.com/user-attachments/assets/31369502-1baa-443f-b1e3-4dbf8a0f5dfc" />
<hr>

### `machine()`

The next function is called `machine()`. It returns the generic name of the processor which runs your OS.

<img width="422" height="105" alt="image" src="https://github.com/user-attachments/assets/e32e1b3c-5ff4-491e-8acd-f4639238bd53" />
<hr>

### `processor()`

A similar function is called `processor()`. It returns the real name of the processor. For some processors, it will print the exact same information as `machine()`.

<img width="767" height="106" alt="image" src="https://github.com/user-attachments/assets/95477a00-820e-4ecd-88a6-62cf6926ab2c" />
<hr>

### `system()`

Next, there is a function named `system()`. This function returns the generic operating system name.

<img width="398" height="98" alt="image" src="https://github.com/user-attachments/assets/27bf3a29-9bb0-4c2c-bd74-f1ab9a28e0c5" />
<hr>

### `python_implementation()`

`python_implementation()` returns the name of your Python implementation. The default value here that you should expect is **CPython**. **CPython** is the default and most widely used implementation of the Python language written in the C language.

<img width="585" height="96" alt="image" src="https://github.com/user-attachments/assets/a4a499d3-7789-456e-b6c2-fd61f3fbb77f" />
<hr>

### `python_version_tuple()`

Finally, `python_version_tuple()`. Unlike all other functions presented in this video, this function does not return a string. Instead it returns a **tuple** with three elements. The first element is the major part of the Python version. The second one is the minor part, and the last one is the patch.

<img width="582" height="86" alt="image" src="https://github.com/user-attachments/assets/e9db49e1-4b14-4b25-be46-bc83b2c251cd" />
