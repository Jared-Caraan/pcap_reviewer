## Binary file basics

Create a new [Jupyter Notebook](https://jupyter.org/try-jupyter/tree/). and call it _misc-file-binary_.

### Binary files
So far we've only worked with text files. Python can also treat files as binary files, but what is the difference between text files and binary files in the first place?

<img width="626" height="338" alt="image" src="https://github.com/user-attachments/assets/c0e66660-2adc-41c9-b4ce-7c4be73b8f9c" /><br>

In a way, there is no difference because both text files and binary files are simply files. Files in the most general sense are just containers for data, and the data is stored as very long sequences of bytes. Sound files with your favorite music, image files with the pictures from your holiday, a simple video game in an executable file are text files. Behind the scenes, they are actually all the same.

These bytes are always organized in a certain way. For instance, image files could be stored as bitmaps with groups of bytes representing individual pixels in the picture.

<img width="647" height="346" alt="image" src="https://github.com/user-attachments/assets/f5212dc4-4ea0-426f-85e3-ee98e14d20a9" /><br>

You then need a specific program on your computer that understands the bitmap format to interpret the bytes correctly as pixels so it can show you a picture as a result.

Other file formats, such as MP three sound files or executable game files, will use bytes in a different way, and you will need different programs to open them.

Python allows you to work with files in two way. The most generic way is to work with files as binary files. In this case, you will need to deal with very raw data that is very hard to handle. Dealing with single bytes could lead to many errors because bytes are harder to reach by human beings. That's why Python also offers another way of working with files, working with files as text files, and you already know how to do that.

<img width="725" height="426" alt="image" src="https://github.com/user-attachments/assets/15f885bb-ec8c-402f-9ef1-e5ae1ddd72d6" /><br>
<hr>

### Byte containers

Python has a few containers for storing sequences of bytes. One of them is a class named **bytearray**. Just as the name suggests, it's an array of bytes and the array is conceptually similar to a python list.

<img width="363" height="76" alt="image" src="https://github.com/user-attachments/assets/9bb6c5ac-1e4b-4082-afc1-031f11203828" /><br>

This line will create an array with 100 bytes and initially they will all equal zero.

<img width="422" height="88" alt="image" src="https://github.com/user-attachments/assets/e0d589d1-075e-4ffa-acec-b2be1f4b4e5f" /><br>

This will set the first byte of the bytearray of the binary representation of the number 100. Remember that the maximal integer you can store in a byte is 255. If you try to store something bigger, you will see an error.

<img width="892" height="282" alt="image" src="https://github.com/user-attachments/assets/19251f49-8ebb-44a4-859d-ab3afbffd729" /><br>
<hr>

### Writing binary

<img width="598" height="267" alt="image" src="https://github.com/user-attachments/assets/6111af35-056d-4908-9dae-39b435ab74ba" /><br>

First of all, look at the second argument for the `open` function. It says `wb`, which stands for _write binary_. This `b` letter is very important because it informs Python that it should not treat the file as a text file. Second of all, note how we passed the binary as an argument for the `write` function. As you can see, the `write` function is quite flexible. If you open the file in the text mode, you can pass strings as arguments. If until you open the file in the binary mode, you can provide bytearray as arguments.

<img width="1212" height="221" alt="image" src="https://github.com/user-attachments/assets/44c54550-71b3-4bbc-bd78-7b7e917e3f33" /><br>

Jupyter is trying to interpret the file as a text file. We set the first two bytes to some random numbers, and Jupyter is trying to interpret them as ASCII characters. After the first two bytes, we didn't do anything. The bytes were set by defaults to zero and bytes zero in the ASCII table represents `null` - a void character that does not contain any data.
<hr>

### Reading binary

<img width="536" height="161" alt="image" src="https://github.com/user-attachments/assets/6cffd169-42a6-4855-a884-82b1bf6b322f" /><br>

We open the very same file that we created earlier on in the `rb` mode, which stands for _read binary_. Then we use the `read` method without arguments to read the bytes.

<img width="1448" height="311" alt="image" src="https://github.com/user-attachments/assets/966f58c6-64ed-4359-a96b-649e0040ded7" /><br>

The print result isn't particularly pretty, but at least we can see that we successfully read the bytearray.

<img width="1517" height="347" alt="image" src="https://github.com/user-attachments/assets/1828de7b-957f-4db1-be11-2ac849557ef3" /><br>

If the binary file is very big, the content of the file may not fit into the available memory. That's why there's also an alternative way to read binary data. You can provide the `read` method with an argument that will denote the maximum number of bytes to read.

<img width="567" height="283" alt="image" src="https://github.com/user-attachments/assets/6e001495-817a-4e9b-bd68-d6b608fce43f" /><br>

