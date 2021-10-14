---
title: Iteration
summary: "The art of executing a set of instructions multiple times with minimal effort"
sidebar: mydoc_sidebar
permalink: mydoc_iteration.html
folder: mydoc
---

## Iteration

Iteration is a technique of repeatedly executing the same set of instructions without explicitly writing the instructions every time we need it repeated. For example, if we want to print all the numbers from 0 to 9 we can do it by writing one `print()` statement and repeat it ten times. We could also write some kind of expression that lets us write only **ONE** `print()` statement and automatically does the rest for us. This is the power of iteration. The most commonly used iteration techniques in Python are **for loops** and **while loops**.

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
    i += 1 # this is the same as i = i + 1
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
