---
title: Taking User Input
summary: "It is important to know how to recieve raw data from the user and process it"
sidebar: mydoc_sidebar
permalink: mydoc_user_input.html
folder: mydoc
---

## Taking Inputs From User

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

{% include links.html %}
