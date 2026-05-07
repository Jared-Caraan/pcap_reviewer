## module platform

### Preface
Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _modules-platform_. The last standard Python module that you need to know for the PCAP examination is called **platform**. The documentation describes it as "access to underlying platforms identifying data". In other words, the platform module can tell you a little bit about your Python version, the operating system, and the hardware you're using.

Take a look at the diagram. It shows the layers between your code and the hardware that your computer is using. Your code is located at the very top level. Below, is the running environment of Python. The next layer is the operating system. Python uses a lot of helpers from the operating system for things such as processing files or communicating with physical devices. At the very bottom, there's the hardware, the processor, the RAM memory, network interfaces, user keyboard and mice, and others. All of the four layers cooperate so we can write Python programs.

*insert picture here of the python env*

For example, when you want to get some user data, your code can invoke the `input()` function. The Python environment accepts the order and adapted to meet the requirements of the local operating system.

### `platform()`

