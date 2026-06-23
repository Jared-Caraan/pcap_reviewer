## Text file writing basics

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-file-write-basics_.

Now that we know how to read text files, let's talk about how to write stuff into text files. The good news is that it's actually simpler than reading files. There's just one method that you should know, and it's called `write`. We also need to modify the open function a bit so that it allows us to write into the file.

<img width="597" height="216" alt="image" src="https://github.com/user-attachments/assets/81c85058-81ab-4afe-b903-1a30c7463018" /><br>

You just have to remember to instruct the `open` function that you want to write into the file, which is why we provide a second argument that `w` stands for right mode. In this case, the new file which doesn't exist will be created by Python automatically for us. Afterwards, we simply use the `write` function as many times as we need. The function does not provide new line characters for us, so we have to provide them ourselves. No matter what the operating system is, Python will take care of translating that for us. Remember to then close the stream at the very end and that's mostly it.

But now what will happen if we try to open the very same file again?

The previous content that we created will be lost. So one thing to keep in mind is that when we use the `w` mode here, Python will either create the file for us or if the file already exists, then it will simply erase all the content from it and to put new content according to the code.
