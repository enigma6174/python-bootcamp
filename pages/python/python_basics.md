---
title: Basics Of Python Programming
keywords: documentation theme, jekyll, technical writers, help authoring tools, hat replacements
last_updated: July 3, 2016
tags: [getting_started]
summary: "I have used this theme for projects that I've worked on as a professional technical writer."
sidebar: python_sidebar
permalink: python_basics.html
folder: python
---

# Introduction To Python Programming : Part 1

Python is the most popular language used for porgramming in the data science domain and a major reason for this is because of it's simplicity. While Python focuses on simplicity and ease of use, at the same time it sacrifices on speed, safety etc. However as a data scientist issues like safety and speed are not of much importance to us right now and when they do, we will use other frameworks designed specifically for production level systems.

In this tutorial we will go through basic Python programming techniques that will be essential in getting started with machine learning, deep learning, data visualization and other data science related programming tasks. This guide is however not comprehensive. It is just a means to get ourselves comfortable with Python. For an in depth Python tutorial you can always refer the officical Python documentation.

_For this tutorial, we will be using Python 3 (Python 3.6 or higher) so please ensure you have Python 3 installed on your computer. A good way to go through these tutorials is to type the commands and execute them along the way._

## The Programming Environment

Python files are saved as `file_name.py` files and running them is quite easy. Here, we will go through 3 of the most popular approaches to Python programming and help you get started:

- **Using Jupyter Notebook**
  This is the easiest approach to getting up and started with Python. This however requires extra software installation (Anaconda). You can download Anaconda distribution from [here.](https://www.anaconda.com/distribution/)
  Once istalled, run Jupyter Notebook, create a new notebook and you can get started immediately. A quick guide to Jypyter Notebook can be found [here.](https://medium.com/codingthesmartway-com-blog/getting-started-with-jupyter-notebook-for-python-4e7082bd5d46)

- **Using A Text Editor**
  A text editor is a program that lets you write code in a language of your choice and provides additional features like _syntax hilighting_, _code completion_ etc. Popular text editors include [Atom,](https://atom.io/) [Sublime Text,](https://www.sublimetext.com/) [Visual Studio Code](https://code.visualstudio.com/) etc. The steps involved are:

* Create a new Python 3 file and write code and save it.
* Open terminal and navigate to the location where the file was saved.
* Type `python3 file_name.py` to execute. If there are no errors, the file will run and the output will be visible on the terminal itself.

- **Using IDE**
  An Integrated Development Environment (IDE) is a software that provides a complete package which includes a text editor, a compiler, a debugger, a project tracker etc. These are however best suited for commercial or production level software development and beginners best stay away from there. That being said, [PyCharm](https://www.jetbrains.com/pycharm/) is a popular Python IDE.

_Alternatively, if you dont want to go through any of the above steps, you can visit [Google Colab](https://colab.research.google.com/notebooks/welcome.ipynb) and execute your Python commands online using Google's servers._

## Topics Covered

- Introduction
  - Printing
  - Formatted Printing
  - Taking Input From User
  - File Handling
  - Data Types
- Loops
  - Different Types of Python Loops
  - How Loops Work
  - Examples
- Conditionals
  - if-else Statements in Python
  - Different Conditional Expressions In Python
  - Examples
- Functions

  - Different Types of Functions
  - Passing Arguments To Functions
  - Returning Values

- Exception Handling
  - Try and Except
  - Else
  - Finally

```python
# This is the command to check the version of Python
# More in import statements later
import sys
print(sys.version)
```

    3.6.7 |Anaconda, Inc.| (default, Oct 23 2018, 14:01:38)
    [GCC 4.2.1 Compatible Clang 4.0.1 (tags/RELEASE_401/final)]

## Introduction

### Printing

The `print()` command is used to output values to the Python console. It supports strings which are enclosed between `'...'` (single quotes) or `"..."` (double quotes). Print also supports variables, functions and data structures like lists, dictionaries etc.

To print a value we type `print('my_string')` or `print("my_string")`. In general, there is no difference between '' and "" in Python. We can also print variable values as `print(my_variable)`. A variable in Python is a container that holds some value. In a more strict way, a variable refers to a location in main memory that holds some value and the name of the variable is how we identify that memory location.

Let us now go through some examples.

```python
# Simple print() statements
print('hello world')
print("hello world")
```

    hello world
    hello world

```python
# Using multiple values in the same print statement
print('hello', 'world')
print('hello ', 'world')
print("hello", " ", "world")
```

    hello world
    hello  world
    hello   world

Note that Python by default adds a space between two print values even though we haven't specified it. For the remainder of the exercises we will be using `"..."` in `print()` statements and string variables and we will be using `'...'` in arguments to function calls.

```python
# Printing variable values
var_num = 12
var_str = "hello world"
f_name = "John"
l_name = "Doe"

print(var_num)
print(var_str)
print(var_num, var_str)
print(f_name, l_name)
```

    12
    hello world
    12 hello world
    John Doe

Python even supports expressions inside `print()` statements. An expression is a combination of variables and operators (like +, - etc.) which results in a value. An expression can also be a conditional expression which we will deal with later.

```python
print(12 - 6) # A simple expression
print(12 ** 2) # 12 raised to the power 2; ** works as power operator in Python
print(4 ** 3) # 4 raised to the power 3
print(5 * 6 + 7 / 8 - 12) # A complex operation
print(7 % 4) # Modulo operation, finds the remainder when 7 is divided by 4
```

    6
    144
    64
    18.875
    3

### Formatted Printing

In formatted printing we embed variables inside a string using `{}` and then we put the variables inside the curly braces to output the contents of the variables. The string itself starts with `f` character which means _format_ and denotes that we are printing a formatted string.

A format string variable has to be defined (ie. declared before used) otherwise it will throw an error.

```python
# Simple formatted output example
var = "hello world"
print(f"this is my first {var} program")
```

    this is my first hello world program

```python
# Formatted output variables can be of different types
var_num = 12
var_str = "John"
print(f"His name is {var_str} and he is {var_num} years old")
```

    His name is John and he is 12 years old

```python
# Using a variable without initializing
print(f"{my_var}")
```

    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    <ipython-input-12-6a30c2ea670a> in <module>()
          1 # Using a variable without initializing
    ----> 2 print(f"{my_var}")


    NameError: name 'my_var' is not defined

This is how an error looks like in Python. We can try to fix our errors using the last error message ouput and slowly working up the chain of command to fix the various errors. In this case there is only 1 error message so there is no chain of command to follow up.

#### format() function

- The `format()` allows us to do more complicated formatting of the string. It is a formatting function which allows multiple substitutions and value formatting.
- This method lets us concatenate elements within a string through positional formatting.
- They work by putting one or more replacement fields and placeholders defined by `{}` which is then filled up by a variable or a value.
- If there are less number of arguments than `{}` we get an error and if there are more number of arguments than `{}` only the first _n_ arguments are considered.

```python
# A simple format() example
formatter = "{} {} {} {}"
print(formatter.format(10, 20, 30, 4.5))
print(formatter.format("hello", "world", 12, True))
```

    10 20 30 4.5
    hello world 12 True

```python
# A complex formatter example
formatter = "{} {} {}"
print(formatter.format(formatter, 12+3-8*4, "hello world 42"))
print(formatter.format(formatter, formatter, formatter))
```

    {} {} {} -17 hello world 42
    {} {} {} {} {} {} {} {} {}

```python
# An even more complex example
formatter = "{} {} {}"
print(formatter.format(formatter.format("a", "b", "c"), formatter, formatter.format(1.23, "hello world", -99)))
```

    a b c {} {} {} 1.23 hello world -99

```python
# Passing more arguments than the number of {}
# Only the first n are considered, in this case n=3
formatter = "{} {} {}"
print(formatter.format(10, -20, 50, -40, -65))
```

    10 -20 50

```python
# Passing lesser arguments than the number of {}
# This will result in an error
formatter = "{} {} {} {}"
print(formatter.format("hello", 12, "world"))
```

    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-21-236069f1b6d7> in <module>()
          2 # This will result in an error
          3 formatter = "{} {} {} {}"
    ----> 4 print(formatter.format("hello", 12, "world"))


    IndexError: tuple index out of range

### Taking Inputs From User

Python lets us take user input using the `input()` function. The `input()` function reads everything as a string. After taking input, we need to _typecast_ the data to relevant type for further processing. _Typecasting_ means to convert the data from one type to another. For eg. if we have to find the sum of 2 numbers, Python will read the input numbers as strings and using a _+_ operations will lead to _concatenation_ (ie. joining the second string to the end of the first string).

However, through typecasting we can convert the data from string to integer format and then add them accordingly. This result will **not be** a concatenation operation, rather it will be a mathematical operation. The following examples will make things clear.

```python
# Simple string input demonstration
print("enter a string : ")
var_str = input()
print(f"entered string is {var_str}")
```

    enter a string :
    hello world
    entered string is hello world

```python
# String concatenation example

print("enter a string : ")
var_str1 = input()
print("enter another string : ")
var_str2 = input()

# Strings are concatenated using + operator
print("concatenated strings are : ", var_str1 + var_str2)
```

    enter a string :
    hello
    enter another string :
    World
    concatenated strings are :  helloWorld

```python
# Concatenation of integers

print("enter a number : ")
var_num1 = input()
print("enter another number : ")
var_num2 = input()

# Concatenation of 2 integers
print(f"The result of {var_num1} + {var_num2} is : ", var_num1 + var_num2)
```

    enter a number :
    12
    enter another number :
    10
    The result of 12 + 10 is :  1210

We can solve the problem of concatenation of numbers using **Typecasting**. Typecasting allows us to convert the string data to any other data type of our choice. This can be achieved by enclosing the `input()` command within the relevant data type.

For eg. to convert string input to integer input we can typecast it as `int(input())`. This will ensure that all the string data is converted to relevant integer data. This however works for numbers. See what happens when the same is applied to string values like _hello world_, _example_ etc.

```python
# Typecasting string input to integer input

print("enter a number : ")
var_num1 = int(input())
print("enter another number : ")
var_num2 = int(input())

# Sum of 2 integers
print(f"The result of {var_num1} + {var_num2} is : ", var_num1 + var_num2)
```

    enter a number :
    12
    enter another number :
    10
    The result of 12 + 10 is :  22

```python
# Typecasting explicit strings to integers
print("enter a string : ")
my_str = int(input())
print("entered string is : ", my_str)
```

    enter a string :
    hello world



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-27-3a882c3431cf> in <module>()
          1 # Typecasting explicit strings to integers
          2 print("enter a string : ")
    ----> 3 my_str = int(input())
          4 print("entered string is : ", my_str)


    ValueError: invalid literal for int() with base 10: 'hello world'

So we get an error which was expected because string representations of numbers can be converted to integers but they will not work with actual strings.

### File Handling

_File Handling_ is the technique of working with files. It involves opening and closing files, reading from files, writing to files etc. We can work with different file types in Python. These include text files, image files, binary files. spreadsheets, CSV files, JSON files etc. However in this example, we will limit ourselves to file operations using text files ie. `.txt` files.

We can open a file using `open(filename)`, close the file using `object.close()` and read the entire contents of the file using `object.read()` commands. Let us first go through some examples and then figure out how basics of file handling works.

```python
# Specify the filename (wrong filename throws error)
filename = "sample.txt"

# Open the file
txt = open(filename)

# Read the contents of the file and print
print(f"CONTENTS OF {filename} : ")
print("=" * 30)
print(txt.read())

# Close the file
txt.close()
```

    CONTENTS OF sample.txt :
    ==============================
    This is a sample line of text.
    This is a text file which has 5 lines.
    The quick brown fox jumps over the lazy dog.
    print("hello world")
    -------------END------------------

#### open(file, mode='r', ...)

`open(...)` is a _function_ that lets us open files on the disk. A _function_ is a pre-defined piece of code that performs a pre programmed task. We will talk more about functions later.

- Open a file and return a stream. Raise I/O Error upon failure.
- `file` is either a text or byte string giving the name of the file to be opened.
- `mode` is an optional parameter that specifies the mode in which the file is opened. Here `mode='r'` means open the file in _read-only_ mode ie. the file can be read from but not written to. Read only mode is the default mode when opening files.
- `open(...)` **does not** return the contents of the file. Rather, it just returns an _object_ of the file which can be used to access the file. An object is a reference to something which gives us the location of the data and other relevant information. For example, we can think of variables as objects of particular data types that tell us where the data is stored in memory.

#### close()

`object.close()` is a function that lets us close the file after we are done using them.

- It is always safe to close files after use to save resources.
- Also, closing a file after use prevents it from getting modified unintentionally.

#### read()

`object.read()` is used to read _n_ bytes from the input stream (in this example, a file). If the size of bytes to read is not specified it will read the whole file.

- The result of `object.read()` can be assigned to a variable which can later be reused.

```python
# Specify the file
filename = "sample.txt"

# Open the file
txt = open(filename)

# Read the first 15 bytes
print(txt.read(15))

# Close the file
txt.close()
```

    This is a sampl

#### write("string")

`object.write("string")` writes "string" to the specified file.

- It takes a parameter of the string we want to write to the file.
- A varible containing string values, a reference to text, combination of string values all can be written to the file.
- To write to a file we must ensure that the file is opened in `'w'` mode and not `'r'` mode.

#### truncate()

`object.truncate()` is a command that is used to empty the contents of the current file.

- `truncate()` command empties the contents of the referenced file to prepare it for writing. Once a file has been truncated we can then write to it using `write(...)` command.
- Actually speaking, opening a file in `'w'` mode clears it altogether but we still need to truncate the file to reset the file pointers to appropriate memory location before starting the write operation.

#### readline()

`object.readline()` reads one line of a text file.

- It scans each byte of the file until it finds the `\n` character and then stops reading the file.
- It then returns whatever it has found so far.
- `object.readline()` also returns the `\n` character at the end of each line (till where it reads) and during printing we might get an extra blank. To prevent this, we can use `print(..., end='')`. This is because by default Python prints every `print(...)` statement on a new line.

#### seek(n)

`object.seek(n)` moves the read/write head (ie. a pointer to where the read/write operation will start) to the n-1 character. This is because the indexing of characters start from 0 position.

- `target.seek(0)` will move the read/write head to the beginning of the file.
- `target.seek(k)` will move the read/write head to the k-1 character in the file. However if k > n (where n is the total number of characters in the file) it will print an empty file.
- `target.seek(-1)` will result in an error and the same is true for any negative value.
- `target.seek(expr)` will move the read/write head to the result of expr-1 (where expr is a mathematical expression and it is evaluated first before moving the pointer. However if the result of expr < 0 then it will throw an error.

```python
# Specify the filename
filename = "sample.txt"

# Open the file in 'w' mode
obj = open(filename, 'w')
```

Trying to read a file before it has been truncated (even though it is opened in 'w' mode leads to error).

```python
# Read the file (this will cause error)
obj.read()
```

    ---------------------------------------------------------------------------

    UnsupportedOperation                      Traceback (most recent call last)

    <ipython-input-36-0f406bcc4cb7> in <module>()
          1 # Read the file (this will cause error)
    ----> 2 obj.read()


    UnsupportedOperation: not readable

We can verify whether the 'w' operation clears a file or not. To do this, simply save the file by _closing_ it and open it again in 'r' mode and then try to read it.

```python
# Close the file
obj.close()

# Open the file again in 'r' mode
obj = open(filename, 'r')

# Read the contents of file and print
print(f"CONTENTS OF {filename}")
print("=" * 30)
print(obj.read())

# Close the file again
obj.close()
```

    CONTENTS OF sample.txt
    ==============================

Let us now write some data to the file.

```python
# Specify the filename
filename = "sample.txt"

# Open the file in 'w' mode
obj = open(filename, 'w')

# Truncate the file to write data
obj.truncate()

# Prepare data to write to file
my_string1 = "the quick brown fox jumps over the lazy dog.\n"
my_string2 = "hello world"
my_string3 = "this is a new line"
my_expr = 12 + 3 - 6 ** 2 * 8 / 12 - 9

# Write some strings to the file
obj.write("this is a new file\n")
obj.write("this line should start on a new line ")
obj.write("this line should also be on a new line ?")
obj.write("\n")

# Write some variable values to the file
obj.write(my_string1 + my_string2)
obj.write(my_string2)
obj.write(my_string3)
obj.write(str(my_expr)) # since 'write()' only takes string data we have to typecast the argument first

# Close the file.
obj.close()
```

Let us now check the file contents of `sample.txt` and then we will go through the other functions on file handling.

```python
# Open the file in read mode
obj = open(filename, 'r')

# Read the contents and display.
print(f"CONTENTS OF {filename}")
print("=" * 30)
print(obj.read())

# Close the file
obj.close()
```

    CONTENTS OF sample.txt
    ==============================
    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0

Let us now see how `target.seek()` and `target.readline()` work and we will be further exploring how to add new data to already existing files, how to open/write to files that do not exist etc.

```python
# Open the file in read mode
obj = open(filename, 'r')

# Print the contents of the file
print(obj.read())
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0

If we now try to read the contents of the file again using `obj.read()` we will get a blank output because the read/write head has moved to the end of the file and there is nothing more to read. To solve this problem, we will need the `seek()` function. If we need to read any particular line of the file instead of the whole file we will use the `readline()` function alongwith the `seek()` function.

```python
# Read the file again
print(obj.read())
```

```python
# Set the pointer to the beginning
obj.seek(0)

# Read the file
print(obj.read())
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0

```python
# Reset the pointer and read the first line
obj.seek(0)
print(obj.readline())
```

    this is a new file

```python
# Reset the pointer and read the first line without extra space
obj.seek(0)
print(obj.readline(), end='')
```

    this is a new file

```python
# Read the next line and set the pointer to the 41st character and print a line from there
print(obj.readline(), end='')
obj.seek(42)
print(obj.readline(), end='')

# Close the file
obj.close()
```

    this line should start on a new line this line should also be on a new line ?
    on a new line this line should also be on a new line ?

#### Modes

- **r** and **r+**
  - This file mode is used to specify that a file is to be opened in _read-only_ mode.
  - A read only mode is a one where the user/program can only read the contents of the file but not modify it.
  - Read mode throws an error when the specified file does not exist. If we want to open a file that does not exist in read only mode without throwing error we have to use **r+**.
- **w** and **w+**
  - This file mode is used to specify that a file is to be opened in _write_ mode which means that the user/program can modify the contents of the file.
  - Opening a file in write mode however empties the contents of the entire file which may not be desirable always.
  - If we want to open a non existing file in write mode without throwing errors, we have to use **w+** mode.
- **a** and **a+**
  - This file mode is used to _append_ data to an already existing file. Appending means to add more contents to the existing file without deleting the contents of the file.
  - Append mode gives permission to modify the contents of the file without deleting it. It starts appending data from current position of the read/write head.
  - If we want to append to a file that does not exist we can do it using **a+** mode without throwing errors.

```python
# Open an existing file in read mode
obj = open(filename, 'r')

# Read the contents of the file
print(obj.read())

# Close the file
obj.close()
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0

```python
# Open the file in append mode
obj = open(filename, 'a')

# Add new contents to the end of the file
obj.write("\n")
obj.write("new line successfully appended!\n")
obj.write("----END----")

# Close the file
obj.close()
```

Now if we open the file we will see that the new data has been appended to the file but the original contents are still intact.

```python
# Open the file in read mode
obj = open(filename, 'r')

# Read the contents of the file
print(obj.read())

# Close the file
obj.close()
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0
    new line successfully appended!
    ----END----

```python
# Open a file in w+ mode (opening this file in w mode will through error as it does not exist on disk)
obj = open("randomXYZ.txt", 'w+')

# Truncate the file for writing
obj.truncate()

# Write some lines to the file
obj.write("hello world")
obj.write("\n")
obj.write("this is a new line\n")
obj.write(str(-99))

# Close the file
obj.close()
```

Let us now go through the contents of the random text file we just created.

```python
# Open the file in read mode
obj = open("randomXYZ.txt", 'r')

# Read the contents
print(obj.read())

# Close the file
obj.close()
```

    hello world
    this is a new line
    -99

```python
# Copy the contents of one file (source) to another (destination) in a single line
source = "sample.txt"
destination = "sampleXYZ.txt"
open(destination, 'w+').write(open(source, 'r').read())

# Append the contents of one file (source) to another (destination) in a single line
source = "randomXYZ.txt"
destination = "sampleXYZ.txt"
open(destination, 'a').write(open(source, 'r').read())

# Open the destination file and display it's contents
obj = open(destination, 'r')
print(obj.read())

# Close the file
obj.close()
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0
    new line successfully appended!
    ----END----hello world
    this is a new line
    -99

### Data Types

The most common data types in Python that are of use to us are `int`, `float`, `str` and `bool`.

- **Integer**
  Integers are non decimal numbers in Python and are represented using `int` keyword.
- **Floating Point**
  Floating point numbers in Python are numbers with fractional parts. They are represented using `float` keyword.
- **String**
  Strings in Python are represented by alphanumeric set of characters and can be numbers, aplhabets or combination of both. They are represented using `str` keyword.
- **Boolean**
  Boolean values in Python are those which have only 2 values. In Python it is represented using `bool` keyword and contains `True` or `False` values.

```python
# Boolean data example
a = bool(1)
b = bool(0)
print(a)
print(b)
```

    True
    False

## Loops

A loop is a technique of repeatedly executing the same set of instructions without explicitly writing the instructions every time we need it repeated. For example, if we want to print all the numbers from 0 to 9 we can do it by writing one `print()` statement and looping over it without hard coding 10 different loop statements. The most commonly used loops in Python are **for loops** and **while loops**.

The body of both the loops contain instructions which we have to execute repeatedly but the instructions are indented inside the loop to indicate they are a part of the loop. Indentation is very important as it is the only way we can group a bunch of instructions under a loop.

- **for loop**

* It is the most commonly used loop in Python and can iterate over a range of values.
* This loop works by first creating a buffer where the iteration indices are stored and then they are referenced to iterate over the actual data structure.
* Since for loop creates the buffer when the loop is first called, changing the indices in the buffer are not possible and therefore we cannot skip over values.
* The `range(a, b)` function in a for-loop includes `a` but excludes `b` so we need to specify `b+1` in order to count `b` also.

- **while loop**

* It is an alternative to the for loop which runs by evaluating a conditional expression.
* As long as the conditional expression evaluates to _True_ the while loop executes and halts immediately when the expression evaluates to _False_.
* This loop does not create a temporary buffer for iteration and can therefore we used for selective iteration.

```python
# Printing numbers from 1 to 10 using for loop
for i in range(1, 11):
    print(i)
print("=" * 10)

# Printing numberd from 1 to 10 using while loop
i = 1
while i < 11:
    print(i)
    i += 1 # this is the same as i = i + 1 ;  not updating the i variable will lead to infinite while-loop iterations
print("=" * 10)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    ==========
    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    ==========

```python
# Print odd numbers from 1 to 20 using for loop
print("for-loop output : ", end='')
for i in range(1, 21):
    print(i, " ", end='')
    i += 2
print("\n")


# Print the odd numbers from 1 to 20 using while loop
print("while-loop output : ", end='')
i = 1
while i < 21:
    print(i, " ", end='')
    i += 2
print("\n")
```

    for-loop output : 1  2  3  4  5  6  7  8  9  10  11  12  13  14  15  16  17  18  19  20

    while-loop output : 1  3  5  7  9  11  13  15  17  19

Notice how the for loop could not print only the odd numbers in the list. This is because when the for loop was first created (beofre the first iteration) a buffer was created containing the numbers from 1 to 21. This buffer cannot be modified and therefore modifying the value of `i` has no effect.

However, the while loop functions differently. The while loop evaluates the expression at every step and does not create the buffer. Hence modifications in the value of `i` reflect in the output. However, it is necessary to modify the variable(s) involved in the conditional expression that is used by the while loop. This is because if the expression remains unchanged, then it is always _True_ and the while loop executes indefinitely.

_A for-loop can only iterate over collection of things whereas a while-loop can do any kind of iteration we want._

## Conditionals

### if-else statements

`if-else` statements in Python are used to transfer the flow of execution to a different part of the program based on the evaluation of a conditional variable or a conditional expression. If the condition evaluates to _True_ or the conditions are met, the `if(...)` part of the code gets executed otherwise the `else(...)` part will get executed.
Similar to loops, all statements under `if` block or `else` block are indented by 4 spaces. These statements _belong_ to the `if` or `else` block.

```python
# Example on if-else statements

var = 1

if var < 10:
    print(f"{var} less than 10.")
else:
    print(f"{var} more than 10.")
```

    1 less than 10.

```python
# Using if-else with for loops

var = 1
flag = True

while flag:
    if var < 10:
        print(f"{var} less than 10.")
        var += 1
    else:
        print(f"{var} more than 10.")
        flag = False
```

    1 less than 10.
    2 less than 10.
    3 less than 10.
    4 less than 10.
    5 less than 10.
    6 less than 10.
    7 less than 10.
    8 less than 10.
    9 less than 10.
    10 more than 10.

### if-elif-else

`if-elif-else` block allows us to branch the program to more than 2 locations. Uing `if-else` block we could branch the program to 2 locations : `if` location and `else` location. However, many times we need to have intermediate checks, other conditions etc. for which either `if` or `else` approach will not work. In such cases, we need intermediate checks between `if` and `else` defined by _else if_ conditions and denoted by the keyword `elif`. The statements under `elif` are also indented by 4 spaces to denote they belong to `elif`. Here are some examples:

```python
# Using if-elif-else with for loops

var = 1
flag = True

while flag:
    if var < 10:
        print(f"{var} less than 10.")
        var += 1
    elif var == 10:
        print(f"{var} equal to 10.")
        var += 1
    elif var > 10:
        print(f"{var} is greater than 10.")
        flag = False
```

    1 less than 10.
    2 less than 10.
    3 less than 10.
    4 less than 10.
    5 less than 10.
    6 less than 10.
    7 less than 10.
    8 less than 10.
    9 less than 10.
    10 equal to 10.
    11 is greater than 10.

In the above code, apart from `if` and `else` blocks we also added an intermediate block `elif` which gave us another branching option for the program : the case when the value of `var` equals 10. This case is intermediate between the value of `var` being less than 10 and the value of `var` being more than 10. With `elif` we could efficiently handle such situations.

### Conditional Expressions

In Python, conditional expressions are expressions that evaluate to **True** or **False**. Below are some of the most commonly used operators in conditional expressions :

- **and**
  - `expr_a and expr_b`
  - It evaluates to **True** when both `expr_a` and `expr_b` are **True** and it evaluates to **False** in any other case.
  - `string_a and string_b` always returns `string_b` if `string_a` and `string_b` are different. The same holds true for numbers.
- **or**
  - `expr_a or expr_b`
  - It evaluates to **True** when either `expr_a` or `expr_b` are **True** or both are **True** and it evaluates to **False** when both are false.
  - `string_a or string_b` always returns `string_a` if `string_a` and `string_b` are different. The same holds true for numbers.
- **not**
  - `not(expr)`
  - It reverses the outcome of the expression `expr`, ie. if the expression evaluates to **False** `not(expr)` will make it **True** and vice versa. Same holds true for **0** and **1**.
- **==** and **!=**
  - The **==** operator is used to test for equality of the left and right hand operands. If both the left and right operands are same it returns **True** otherwise it returns **False**.
  - It is denoted by `expr_a == expr_b`.
  - The **!=** operator is used to test for inequality of the left and right hand operands. If both the left and right hand operands are different it returns **True** otherwise it returns **False**.
  - It is denoted by `expr_a != expr_b`.

#### Note:

- In all cases `expr_a` and `expr_b` are operands. They can be expressions, values returned by functions, constants, variables etc.
- The **and** and the **or** operator are not affected by size of the operands ie. they do not consider the size of the operands when making a comparison.
- **=** is the assignment operator for eg. `a = b` and assigns the value of `b` to `a`.
- Operators **<** , **>**, **<=**, **>=** are self explanatory and have the same effect as their mathematical equivalent (_less than_, _greater than_, _less than or equal to_, _greater than or equal to_).

```python
expr = 'test' == 'testing'
print("'test' == 'testing' ", expr)

expr = 'test' != 'testing'
print("'test' != 'testing' ", expr)

expr = True and False
print("True and False ", expr)

expr = True and 1
print("True and 1 ", expr)

expr = True or False
print("True or False ", expr)

expr = not(True or 0)
print("not(True or 0) ", expr)

expr = 'hello' and 'world'
print("'hello' and 'world' ", expr)

expr = 'hello' and 'boy'
print("'hello' and 'boy' ", expr)

expr = 'hello' or 'world'
print("'hello' or 'world' ", expr)

expr = 1 == 1 and (not('testing' == 1 or 1 == 0))
print("1 == 1 and (not('testing' == 1 or 1 == 0)) ", expr)
```

    'test' == 'testing'  False
    'test' != 'testing'  True
    True and False  False
    True and 1  1
    True or False  True
    not(True or 0)  False
    'hello' and 'world'  world
    'hello' and 'boy'  boy
    'hello' or 'world'  hello
    1 == 1 and (not('testing' == 1 or 1 == 0))  True

```python
# Examples to show the other operators

i = 1
j = 1
flag = True

while flag:

    j += 3

    if i < 10:
        print(i, " ", end='')
        i += 1

    elif i >= 10 and i <= 20:
        i += 3
        j += 5
        print(i, " ", end='')

    elif i > 20 or j % 5 == 0:
        print(j, " ", end='')
        flag = False

    else:
        print(i)
        flag = False
```

    1  2  3  4  5  6  7  8  9  13  16  19  22  63

## Functions

A function represents a group of instructions that perform a particular task. For example, we can have a function that calculates the square of a number, a function that prints a string in reverse order, a function that contains a loop and executes a particular task repeatedly. Functions are defined as `def function_name(...)` where `function_name` can be anything (as long as it is not a reserved keyword and follows the same rules as naming variables). The `()` after a name specify it is a function. For example `var` is a variable whereas `var()` is a function. The `...` inside the paranthesis of the funciton mean that we can also put extra information inside the function. The `def` is a keyword that tells the Python compiler that this is a function and all code indented below this is a part of the function.

Consider the following example :

> `def foo(): print("Hello") print("World)`

The above is a basic definition of a function. Here, the paranthesis do not contain anything which means the function does not take any _parameters._

**Function Parameters** These are the values that are passed to the function at the time of function definition. The function uses these values to perform a particular task, change the state of some variable or output something.

Consider the following example :

> `def foo(a, b):

    c = 10
    if a > b:
        c -= a
    else:
        c += b
    print(c)`

The above function takes 2 values at the time of creating the function which are the variables `a` and `b`. After some processing, the function changes some internal variable `c` and prints the result.

**Calling A Function** When we write the name of the function anywhere in the code (after the function has been properly created) we are said to _call_ the function. In other words, _calling a function_ means executing a function after it has been created. This execution can happen anywhere in the code at any time during the execution.

Consider the following example (we will be using the first `foo()` function as a reference, assume it has been created) :

> `var = 10
> while var % 2 == 0:

     if (var * 2 + 1) % 3 == 0:
         foo()
     else:
         print("done!")
     var += 1

foo()`

In the above example, we executed the `foo()` function twice, once inside the `if` statement block and the again inside the `while` statement block in the end. This is called calling a function.

```python
# Simple function example
def foo():
    print("Hello World!")

# Function with parameters
def even(var):
    if var % 2 == 0:
        print("even")
    else:
        print("odd")

# Call the first function
foo()

# Take user input
x = int(input())

# Call the second function passing x to the parameter
even(x)
```

    Hello World!
    12
    even

**Arguments** The values that are passed as parameters to the function during runtime (ie. when the function is called) are called as arguments. They are different from parameters because parameters are defined inside the function at the time of creation and are always fixed. Parameters cannot change without modifying the function. Arguments on the other hand are variables and whichever variable is passed to the function call is considered as an argument.

In the above example in the second function `even(var)` the parameter is `var` whereas when the function is called after taking user input the argument is `x` because this is the variable that is passed at runtime.

### Different Types Of Functions

- **Functions which take no parameters and do not return anything back to the program.** These are the functions that do not modify the source code, rather they are used to perform simple repeating tasks like printing a particular message. However if these functions have access to variables belonging to the main program, they can be used to modify the source code.

- **Functions that take arguments but do not return anything back to the program.** These are the functions that have parameters defined inside them and they use the values inside the parameters to give some information about the data of the main program. For example, they can be used to check if a number is even or odd, if a string is a palindrome etc. They can also be used to modify the values of the variable(s) of the main code to which they have access. Functions that are defined by parameters can take any type of arguments. The arguments can be variables, expressions, another function (return value), a list, a dictionary etc.

- **Functions that do not take arguments but return a value back to the program.** These functions always end with the keyword `return` and send something back to the main program which called the function in the first place. Since it does not take parameters it can only return information stored inside the function when it was created. For eg. we can have information retrieval functions which return the name of person when called. We can also have functions which return the current time or date etc. all of which do not require parameters but perform some type of information retrieval.

- **Functions that take arguments and return a value back to the program.** These functions also end with the keyword `return` but because they take arguments, these types of functions are the most versatile and powerful. They can be used for almost anything for eg. calculating the square of a number, taking an input string and reversing it etc.

#### Note:

- Python allows a default value to be set for the parameter. This means that if during function call the argument is not passed, then the function calculates using the default value.
- All instructions in Python function are indented with 4 spaces.
- We can even take input inside a function call as arguments.
- The number of arguments that can be passed to a function depends on the Python version but it is best practice to keep number of arguments less than 5.
- If we have functions nested inside functions, then the innermost function is the last to get called but first to get executed. Think of it like a stack approach to a function call.
- `len` is a Python function that gives the number of bytes present in a string.

```python
# Function that takes nothing, returns nothing
def foo():
    print("Hello World")

# Function that takes a parameter
def even(var):
    if var % 2 == 0:
        print("even")
    else:
        print("odd")

# Function that returns a value but does not take parameters
def fun():
    return "hello world"

def funl():
    return len("hello world")

# Function that takes paramters and returns a value
def power(x, y):
    return x ** y

# Function with default parameters
def f(a=10, b=20, c=3):
    return a + b * c
```

```python
# Call the first function
foo()

# Take user input and call the second function
x = int(input("number?"))
even(x)

# Call the third function and print the returned value
var = fun()
print("fun() returns ", var)

# Take 2 user inputs and pass them to the fourth function and print the returned value
x = int(input("number?"))
y = int(input("number?"))
var = power(x, y)
print(f"{x} raised to the power {y} is {var}")
```

    Hello World
    number?13
    odd
    fun() returns  hello world
    number?9
    number?3
    9 raised to the power 3 is 729

### Passing Arguments To Functions

Though arguments can be passed to a function in many different ways, in this tutorial we will limit ourselves to variables, function call returns, inputs and expressions.
_Passing data structures as arguments will be covered in the second part of this tutorial._

```python
# Passing an input call as argument
even(int(input("number?")))
```

    number?19
    odd

```python
# Passing an expression and a variable as input call
expr = 6 - (4 * (5 + 3 * (2 - 4)) - 7)
var = power(18 - 4 * 3, expr)
print(f"6 to the power {expr} is {var}")
```

    6 to the power 17 is 16926659444736

```python
# Passing a function return value as an argument
even(funl())
```

    odd

```python
# Checking the output of funl()
print(funl())
```

    11

```python
# A difficult function call
var = power(funl(), int(input("number?")))
print(f"{funl()} to the power _ is {var}")
```

    number?3
    11 to the power _ is 1331

```python
# Calling the function f without default paramters
print(f(funl(), funl() * 2, funl() * 2 + 3))

# Calling the function f with all default parameters
print(f())

# Calling the function f with some default parameters
print(f(expr))
```

    561
    70
    77

### Returning Values

Python allows functions to return multiple values. It can also return a list, a dictionary etc. which will be coverd in the second part of the tutorial but for now let us focus how to return multiple values through functions.

```python
# Function that returns multiple values
def foo(a, b):
    c = 2 * a + b
    return a, b, c
```

```python
# Receiving multiple return values from function call
x, y, z = foo(10, 20)
print(x, y, z)
```

    10 20 40

```python
# Function that returns another function call
def foo(a, b):
    c = funl() * a + b
    return c, funl(), c % funl()
```

```python
# Receiving multiple return values from function call
x, y, z = foo(4, 7)
print(f"c={x}, funl()={y}, c%funl()={z}")
```

    c=51, funl()=11, c%funl()=7

```python
# Function that returns multiple data types
def foo(a, b):
    c = funl() * a + b
    return c, fun(), c % 2 == 0
```

```python
# Receiving multiple return values from function call
x, y, z = foo(4, 7)
print(f"c : {x}, fun() : {y}, c%2==0 : {z}")
```

    c : 51, fun() : hello world, c%2==0 : False

## Exception Handling

A Python program terminates when it encounters an error. In Python programming there are two types of errors : **Syntax Error** and **Exceptions**

- **Syntax Errors** are errors which arise because of wrong syntax in the code. This is because the Python compiler fails to understand the Python code. For example consider the following code :

> `print("hello world)
> print((hello world")
> if a < b

       do_something()

else:
do_something_else()
`

The first two `print()` statements are written in wrong syntax because of missing double quotes `"`. Similarly, the `if` statement is syntactically wrong because of missing `:`. These will lead to syntax errors because the Python compiler will fail to recognise them as Python instructions.

- **Exceptions** are errors which are detected during runtime ie. during program execution. In these errors, the code is syntactically correct but due to some failure at runtime exceptions occur. For example, dividing by zero trying to open a file which does not exist etc. all lead to exceptions. Exceptions are hard to debug because the Python compiler will not detect them during compiliation.

In this section, we will go through what exceptions are, how they differ from sytax errors and how to handle exceptions in our program.

```python
# Syntax error example
print("hello world)
```

      File "<ipython-input-1-b381606234b4>", line 2
        print("hello world)
                           ^
    SyntaxError: EOL while scanning string literal

```python
# Syntax error example
a = 10
b = 20

if a < b
    print(a)
else:
    print(b)
```

      File "<ipython-input-2-115c41438573>", line 5
        if a < b
                ^
    SyntaxError: invalid syntax

```python
# Exception example
a = 100;
i = 10

while i >= 0:
    a = a / i
    print(a)
    i -= 2
```

    10.0
    1.25
    0.20833333333333334
    0.052083333333333336
    0.026041666666666668



    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    <ipython-input-3-4e8cc6752d4d> in <module>()
          4
          5 while i >= 0:
    ----> 6     a = a / i
          7     print(a)
          8     i -= 2


    ZeroDivisionError: float division by zero

```python
# Exception example
filename = "some_random_file.txt"
txt = open(filename, 'r')
print(txt.read())
```

    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    <ipython-input-4-7392a10d950d> in <module>()
          1 # Exception error
          2 filename = "some_random_file"
    ----> 3 txt = open(filename, 'r')
          4 print(txt.read())


    FileNotFoundError: [Errno 2] No such file or directory: 'some_random_file'

```python
# Opening a non existent file in 'w+' mode will not lead to exception
filename = "some_random_file.txt"
txt = open(filename, 'w+')
print(txt.read())
```

```python
# Opening a non existent file in 'r+' mode will lead to exception
filename = "another_random_file.txt"
txt = open(filename, 'r+')
print(txt.read())
```

    ---------------------------------------------------------------------------

    FileNotFoundError                         Traceback (most recent call last)

    <ipython-input-7-d9b68c2209db> in <module>()
          1 # Opening a non existent file in 'r+' mode will lead to exception
          2 filename = "another_random_file.txt"
    ----> 3 txt = open(filename, 'r+')
          4 print(txt.read())


    FileNotFoundError: [Errno 2] No such file or directory: 'another_random_file.txt'

Now that we know how to distinguish between syntax errors and exceptions let us see what are the common Python exceptions that we might encounter :

- **IOError** This exception occurs when a specified file cannot be opened by the program. The file may or may not exist, but there is some error while trying to open it.
- **KeyboardInterrupt** This exception occurs when an unwanted key is pressed by the user at runtime.
- **Value Error** This exception occurs when a built in function receives a wrong argument.
- **EOFError** If end-of-file is reached without reading any data.
- **ImportError** If the required module cannot be found.

### Exception Handling Using Try and Except Block

The `try` and `except` block in Python are used to _catch and handle_ exceptions. _Catching_ an exception means to detect an exception when it occurs and _handling_ and exception means to take appropriate steps after detection of exception to prevent the program from crashing. This enables the program to carry out normal execution even after an exception occurs.

In the `try` block Python runs the _normal_ code ie. the regular instructions that are a part of the program. In the `except` block we include code that handles any exceptions that might occur in the preceeding `try` block. It is important to note that only the code which handles the exception goes into the `except` block. Let us see this with an example:

```python
# Handling division by zero error
def divide(a, i):
    try:
        while i >= 0:
            a = a / i
            print(a)
            i -= 2
    except:
        print("Division By Zero Exception!")

divide(100, 10)
```

    10.0
    1.25
    0.20833333333333334
    0.052083333333333336
    0.026041666666666668
    Division By Zero Exception!

```python
# Handling file not found exception
try:
    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())
except:
    print("File Not Found exception!")
```

    File not found exception!

> **WARNING** Catching exceptions hides all errors, even those which are unexpected. That is why it is considered best practice to avoid bare except clauses in our Python programs. Rather, refer to specific exception classes that we want to catch and handle.

The following example will make things clear why we need specific `except` clauses instead of bare ones.

```python
# Example which shows what happens when we dont use exact except clauses
try:

    # Opening a file exception
    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())

    # Divide by zero exception
    var = 100 /  0
    print(var)

except:
    print("Exception!")
```

    Exception!

```python
# Example to handle specific exceptions
try:
    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())

    var = 100 / 19
    print(var)
except FileNotFoundError as fnf_err:
    print("\nException Caught : ", fnf_err)
except ZeroDivisionError as zde_err:
    print("\nException Caught : ", zde_err)
```

    Exception Caught :  [Errno 2] No such file or directory: 'newfile.txt'

```python
# Example to handle specific exceptions
try:
    filename = "sample.txt"
    txt = open(filename, 'r')
    print(txt.read())

    var = 100 / 0
    print(var)
except FileNotFoundError as fnf_err:
    print("\nException Caught : ", fnf_err)
except ZeroDivisionError as zde_err:
    print("\nException Caught : ", zde_err)
```

    this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0
    new line successfully appended!
    ----END----

    Exception Caught :  division by zero

```python
# Example to handle both exceptions
try:
    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())

    var = 100 / 0
    print(var)
except FileNotFoundError as fnf_err:
    print("\nException Caught : ", fnf_err)
except ZeroDivisionError as zde_err:
    print("\nException Caught : ", zde_err)
```

    Exception Caught :  [Errno 2] No such file or directory: 'newfile.txt'

As evident from the above example, it is clear that the program executes only till the first exception. If the later part of the program is correct under the try block it still does not get executed (refer third example from last). There are different ways to handle them and we will be looking thorugh a few of them.

Here are some important points to remember:

- A try caluse is executed up until the point where the first exception is encountered ie. if there is no exception **only** the try clause will run and if there is an exception, everything after the exception in the try clause will be skipped and the program will jump to the except clause.
- Inside the excpetion handler (ie. the except clause) the programmer can decide how to handle the exception.
- We can anticipate multiple exceptions and differentiate how the program should respond to them (ie. a try statement can have more than one except clause).
- If an exception occurs but the exception handler cannot handle it, it is passed to outer try statements. If the exception is left unhandled, the execution stops.
- It is better to avoid bare exception clauses.

### The Else Clause

Python allows us to execute a certain piece of code if there are no exceptions using the `else` statement. This is a useful way to handle multiple exceptions that might arise in the try block or if the code gets skipped (in a try block) due to some earlier exception.

```python
# Consider an earlier example
try:
    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())

    var = 100 / 17
    print(var)
except FileNotFoundError as fnfe_err:
    print("EXCEPTION CAUGHT : ", fnfe_err)
except ZeroDivisionError as zde_err:
    print("EXCEPTION CAUGHT : ", zde_err)
```

    EXCEPTION CAUGHT :  [Errno 2] No such file or directory: 'newfile.txt'

In this example, the division operation gets skipped because of an exception caught above. This problem can be solved using `else` statement along with `try` and `except` clause. Consider the example below:

```python
# Else statement with try and except
try:
    var = 100/7
    print(var)
except ZeroDivisionError as zde_err:
    print("EXCEPTION CAUGHT : ", zde_err)
else:
    try:
        filename = "newfile.txt"
        txt = open(filename, 'r')
        print(txt.read())
    except FileNotFoundError as fnfe_err:
        print("EXCEPTION CAUGHT : ", fnfe_err)
```

    14.285714285714286
    EXCEPTION CAUGHT :  [Errno 2] No such file or directory: 'newfile.txt'

From the above example we can see that the `else` block solves the previous problem. However, this is not an elegant solution because the `else` block is executed **only when there are no exceptions.** If the division would have resulted in an exception then the `else` block would have been ignored altogether.

A simple solution to this problem is to use nested `try-except` blocks. Consider the following example:

```python
# Using nested try except block
try:

    try:
        var = 100 / 0
        print(var)
    except ZeroDivisionError as zde_err:
        print("EXCEPTION CAUGHT : ", zde_err)

    filename = "newfile.txt"
    txt = open(filename, 'r')
    print(txt.read())

except FileNotFoundError as fnfe_err:
    print("EXCEPTION CAUGHT : ", fnfe_err)
```

    EXCEPTION CAUGHT :  division by zero
    EXCEPTION CAUGHT :  [Errno 2] No such file or directory: 'newfile.txt'

Even though there are multiple exceptions being raised, all of them get caught because of the nesting of `try-except` blocks. An even better solution is to use multiple nested `try-except` blocks for those parts of the code where we can anticipate an exception. Becuase of the nesting, all unhandled excpetions from inner `try-except` blocks will get passed to the outer ones which will try to handle them or pass them higher up. This reduces the chances of the program crashing drastically.

```python
# Multiple nested try except block
try:

    try:
        var = 100 / 0
        print(var)
    except ZeroDivisionError as zde_err:
        print("EXCEPTION CAUGHT : ", zde_err)

    try:
        filename = "newfile.txt"
        txt = open(filename, 'r')
        print(txt.read())
    except FileNotFoundError as fnfe_err:
        print("EXCEPTION CAUGHT : ", fnfe_err)

    try:
        var = 56 / 0
        print(var)
    except ZeroDivisionError as zde_err:
        # this will be an unhandled exception which will get handled by outer try-except block
        print("EXCEPTION CAUGHT : ", zde)
except:
    print("UNKNOWN EXCEPTION CAUGHT WHILE TRYING TO HANDLE ANOTHER EXCEPTION!")
```

    EXCEPTION CAUGHT :  division by zero
    EXCEPTION CAUGHT :  [Errno 2] No such file or directory: 'newfile.txt'
    UNKNOWN EXCEPTION CAUGHT WHILE TRYING TO HANDLE ANOTHER EXCEPTION!

### The Finally Clause

The `finally` clause ensures that Python **always** runs some code after `try-except` execution. This is mostly used for cleaning up operations but the code in `finally` will always run with or without any previously encountered exceptions.

```python
# An example on how finally clause works
try:

    try:
        var = 100 / 0
        print(var)
    except ZeroDivisionError as zde_err:
        print("EXCEPTION CAUGHT : ", zde_err)
        print("\n")

    try:
        filename = "sample.txt"
        txt = open(filename, 'r')
        print(f"CONTENTS OF {filename} :\n", "-" * 30, "\n", txt.read(), "\n")
    except FileNotFoundError as fnfe_err:
        print("EXCEPTION CAUGHT : ", fnfe_err)
        print("\n")

    try:
        var = 56 / 0
        print(var)
    except ZeroDivisionError as zde_err:
        # this will be an unhandled exception which will get handled by outer try-except block
        print("EXCEPTION CAUGHT : ", zde)
        print("\n")

    # this code will not execute because of unhandled exception
    txt.close()
    print("[1]. File closed!\n")
except:
    print("UNKNOWN EXCEPTION CAUGHT WHILE TRYING TO HANDLE ANOTHER EXCEPTION!\n")
finally:
    # because of finally we can close the file here
    txt.close()
    print("[2]. file closed!")
```

    EXCEPTION CAUGHT :  division by zero


    CONTENTS OF sample.txt :
     ------------------------------
     this is a new file
    this line should start on a new line this line should also be on a new line ?
    the quick brown fox jumps over the lazy dog.
    hello worldhello worldthis is a new line-18.0
    new line successfully appended!
    ----END----

    UNKNOWN EXCEPTION CAUGHT WHILE TRYING TO HANDLE ANOTHER EXCEPTION!

    [2]. file closed!

### CONCLUSION

Congratulations! You have made it till the end of the first part of the tutorial. If you have been going through these tutorial, a good idea would be to implement them on your computer typing by hand and executing the code. You are also encouraged to try and make modifications to this code and see what happens.

You can alternatively, use the provided **.py** files and run them directly using the command `python3 filename.py` on your terminal and check the output.

{% include links.html %}
