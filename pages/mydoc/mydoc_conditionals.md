---
title: Conditionals
summary: "Working with logic and applying condtions and checks to achieve different results from the same point"
sidebar: mydoc_sidebar
permalink: mydoc_conditionals.html
folder: mydoc
---

# Conditionals

## if-else statements

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

## if-elif-else

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

## Conditional Expressions

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

### Note:

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

{% include links.html %}
