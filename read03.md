# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## Read & Write Files in Python
#### What Is a File?
  a file is a contiguous set of bytes used to store data. This data is organized in a specific format and can be anything as simple as a text file or as complicated as a program executable. In the end, these byte files are then translated into binary 1 and 0 for easier processing by the computer.
file systems are composed of three main parts:
+ Header: metadata about the contents of the file (file name, size, type, and so on)
+ Data: contents of the file as written by the creator or editor
+ End of file (EOF): special character that indicates the end of the file
### Opening and Closing a File in Python

When you want to work with a file, the first thing to do is to open it. This is done by invoking the open() built-in function. open() has a single required argument that is the path to the file. open() has a single return,close() for close the file

Other options for modes are fully documented online, but the most commonly used ones are the following:
  + with open('dog_breeds.txt', 'r') as reader:

| Character    | Meaning |
| ---       | ----------- |
| 'r'  | Open for reading (default) |
| 'w'  | Open for writing, truncating (overwriting) the file first |
| 'rb' or 'wb'  | Open in binary mode (read/write using byte data) |

## Exceptions in Python
We can use raise to throw an exception if a condition occurs. The statement can be complemented with a custom exception.
- ![Big O ](https://files.realpython.com/media/raise.3931e8819e08.png)
+ raise allows you to throw an exception at any time.
+    assert enables you to verify if a certain condition is met and throw an exception if it isn’t.
- ![Big O ](https://files.realpython.com/media/try_except_else_finally.a7fac6c36c55.png)
+    In the try clause, all statements are executed until an exception is encountered.
+    except is used to catch and handle the exception(s) that are encountered in the try clause.
+    else lets you code sections that should run only when no exceptions are encountered in the try clause.
+    finally enables you to execute sections of code that should always run, with or without any previously encountered exceptions.
