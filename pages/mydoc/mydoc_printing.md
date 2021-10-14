---
title: Working With Print Statements
summary: "Understanding the most basic feature of any programming language - how to print to the console"
sidebar: mydoc_sidebar
permalink: mydoc_printing.html
folder: mydoc
---

## Printing

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

## Formatted Printing

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

### format() function

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

{% include links.html %}
