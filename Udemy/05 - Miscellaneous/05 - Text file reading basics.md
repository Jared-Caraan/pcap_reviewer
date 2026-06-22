## Text file reading basics

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-file-read-basics_.

### Sample file processing

<img width="557" height="173" alt="image" src="https://github.com/user-attachments/assets/9fe5dea7-44a6-4170-9bcf-c5484abc476b" /><br>

First of all, the whole code is enclosed in a try-except block. That's because with file processing, a lot of things may go wrong: a given file may not exist, you may not have access to it, it may be corrupted and so on. That's why it's always a good idea to use a try-except block and somehow handle the exception.

Inside the try-block you can see two very important instructions - the first line opens the file by calling the `open` function with a single argument. This is the most basic version of the open file you can find. The result of the function should be assigned to a variable. Otherwise, you will not be able to do anything with the file handler or file stream.

The last line in the try-block should be a method named `close` invoked on the stream object. It's very important that you close every stream that you open. Otherwise, you may run into memory problems very quickly.

Let's try to invoke the code twice, once with a valid existing file name and to once with an invalid name.

<img width="537" height="162" alt="image" src="https://github.com/user-attachments/assets/39de349c-152a-4dd9-9280-4f7c0b95a295" /><br>

As you can see with a valid name, we don't see anything in the output. That's because our program doesn't do anything with the file yet. It just opens and closes it. But if we don't see any output, it's actually a good sign, it means that Python successfully accessed the file.

Now let's change the file name to something that doesn't exist and let's see what happens.

<img width="858" height="195" alt="image" src="https://github.com/user-attachments/assets/2f418e18-7c56-4113-88f3-830ecdb6af7c" /><br>
<hr>

### Actual file operations

#### `read`

<img width="668" height="252" alt="image" src="https://github.com/user-attachments/assets/3a8f006f-de62-4297-bab8-33a533e4de78" /><br>

The `read` method is the most basic way of reading the content of a file. By default, it returns the whole content of the file, which you can conveniently print to the output. If you want to, you can also specify the number of bytes that should be read, and each byte typically means one character.

<img width="507" height="197" alt="image" src="https://github.com/user-attachments/assets/597311b3-0351-4730-9c31-c899d88ce260" /><br>

You can see the first ten characters printed to the output.

Once you read the first ten bytes, the stream moves inside the file. If you invoke read ten again, you will see the next ten bytes.

<img width="537" height="242" alt="image" src="https://github.com/user-attachments/assets/2978cf3e-705a-4db7-b0e6-f9393c101713" /><br>

And what happens when the stream reaches the end of a file? It returns an empty string.

<img width="651" height="260" alt="image" src="https://github.com/user-attachments/assets/97d7da23-fab9-4915-845d-7de760ebbf89" /><br>

So note two things, if you ask Python to read more bytes than there are in the file, nothing bad will happen. Python will simply return the string with all the characters in the file and the pointer in this stream will be set at the very end of the file, so any subsequent read call will just return an empty string.
<hr>

#### Counting each character

<img width="1236" height="425" alt="image" src="https://github.com/user-attachments/assets/eb5339e5-d20b-4132-b9e7-884b79e1932f" /><br>

Reading a text file, character by character also has another advantage. You protect yourself against corrupting your operating system in terms of very big files. If the text file you're trying to read is a terabyte long file, then trying to read it all at once using the `read` method without any argument will probably make your program crash. The file is simply too big to be read all at once. In such cases, using `read(1)` and reading the file character by character protects you against such cases.
<hr>

#### Reading line by line

<img width="682" height="407" alt="image" src="https://github.com/user-attachments/assets/0d0fbeb6-4956-4d4a-bdae-2e9333ea3ce7" /><br>

It behaves similarly to `read`. When it reaches the end of the file, it returns an empty string.

Note that even though we instruct the `print` function not to put a new line character at the end of the `print` invocation, the lines are still shown in the output separated by new line characters. That's because each line read from the file contains a new line character at the end by itself.

One more method worth mentioning is `readlines()`. If you invoke this method without any argument, it reads all the file contents line by line and returns a list of strings. One string per file line. Again, if the file you're trying to read is very big, you may run into performance problems.

<img width="1422" height="420" alt="image" src="https://github.com/user-attachments/assets/090e4dfe-cb95-46d8-9183-7e0a1cee0aef" /><br>

<img width="737" height="398" alt="image" src="https://github.com/user-attachments/assets/1255b448-d9fa-43c5-8a38-291394e68c30" /><br>

Typically, reading more than one line at a time means better performance. But remember that reading all the lines at once may crush your program if the text file is very big.

Finally, there's one more way you can reach files line by line. You may use the stream itself. That's because by default, the stream that you get by calling the open function is an object that is iterable. Iterable objects can be iterated using the full loop, just like sequences. This way the stream will return another line of the file in each iteration of the loop, and it turns out that you don't even need to close the stream if you use this technique. When you reach the end of the stream with this technique, Python will automatically close the stream for you.

<img width="666" height="241" alt="image" src="https://github.com/user-attachments/assets/9779e4ff-b3da-459e-ac10-79c49c8fc5e3" /><br>
