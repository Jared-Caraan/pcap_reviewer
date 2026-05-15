## Module locations: `sys.path`

So far we have learned two types of modules imported into our Python files. Modules from the standard Python library and our own custom modules. In both cases, we only had to write a single line such as `import` - followed by the name of the module. Without the file extension, we did not need to specify where Python could actually find the module. We know that the custom modules created by ourselves could be found in the same directory as the main file.

But how about the standard library? How did Python know where to look for the _random module_, for example? In fact, there's a special variable in Python which stores a list with all the directories that Python should check in order to find a module that we request with the _import_ keyword.

We can check that variable by importing the _sys_ module and accessing the _path_ variable.

<img width="1340" height="871" alt="image" src="https://github.com/user-attachments/assets/a6311a1e-4ede-4508-8f50-637f7098b33e" /><br>

Take a look at the output. Python prints a list of all locations where it checks for modules. The locations are checked in the same order as they appear in the list. As soon as Python finds a given module, it imports it and doesn't check the rest of the list. This means that if you have two versions of the same module in two different locations from the list, Python will simply take the first one that it finds and will ignore the other one completely. If Python can't find the module in any of the specified locations, the _import_ fails and we can see an error in the output.
<hr>

### `sys.path.append()`

Interestingly, we can add new locations to the _path_ variable using `sys.path.append()`. You could use that functionality if you wanted to place your modules into a non-standard folder and still ask Python to look for the modules there.

This is before `sys.path.append()`.

<img width="1531" height="861" alt="image" src="https://github.com/user-attachments/assets/974a6da9-fdff-4933-aa7e-dd458abb3e23" /><br>

And this is after the functionality is used.

<img width="1535" height="892" alt="image" src="https://github.com/user-attachments/assets/59d2db12-ea2e-4922-b8bf-2eab08e7086a" />

If you try to write `import sys, secret module` on line 1, you will get an error because on this line the secret folder is not added to the path variable yet.

Additionally, you can add both relative and absolute paths. Absolute path is the full address of the folder, starting from the hard drive label.

<img width="380" height="58" alt="image" src="https://github.com/user-attachments/assets/b15bc5ab-ca0e-41c5-a5e7-d54164065c0c" /><br>

> [!IMPORTANT]
> Use double slashes for absolute and relative paths

Lastly, if you want to have a relative path that goes up in the folder hierarchy, keep in mind that the command to go one folder up in Python is represented by two dots.

<img width="425" height="57" alt="image" src="https://github.com/user-attachments/assets/80943f49-ea8f-445f-9e99-6c531e434ff2" />
