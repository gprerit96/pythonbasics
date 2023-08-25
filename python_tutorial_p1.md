---
layout: default
title: Python Tutorial Part 1
nav_order: 99
---

# Introduction to Python
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

- TOC
{:toc}


## Python Installation

If you already have a Python distribution installed, you can still use it for this class. However, you will need to install some packages using `pip` or `conda`, and it is your responsibility to make sure your code runs in the environment specified above. If you are not familiar with `pip` or `conda`, you should install Anaconda.

![Anaconda](assets\anaconda.png)

In this class, you need a Python 3.10 distribution. The best way to get it is to install [Anaconda](https://www.anaconda.com/products/individual). Anaconda is a Python distribution that comes with a lot of useful packages for scientific computing. It also comes with a package manager called `conda` that makes it easy to install, uninstall, and update packages.

During the installation, you will be asked whether you want to add Anaconda to your `PATH` environment variable. 

> A PATH variable is an operating system construct. It is a list of directories where the operating system will look for executable files when you type a command in the terminal. For example, when you type `python` in the terminal, the operating system will look for an executable file called `python` in the directories listed in the PATH variable. If it finds it, it will run it. If it doesn't, it will give you an error.

![Anaconda PATH](assets\path.png)

If you are not sure, you should say yes. If you say no, you will need to activate the Anaconda environment every time you want to use it. If you are not sure what this means, you might say yes (for convenience) or ask for help.

The other question you will be asked is whether you want to register Anaconda as your default Python. If you say yes, Anaconda will add its Python distribution to the PATH variable. This would allow you to run Python from the command line while also allowing you to use other programs like VS Code to run Python. It is recommended that you say yes.


After installation, you should be able to run Python from the command line. Open a terminal and type `python`. You should see something like this:

```
Python 3.10.9 | packaged by Anaconda, Inc. | (main, Mar  1 2023, 18:18:15) [MSC v.1916 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 
```

Then, run `conda -V` to check the version of `conda`. You should see something like this:

```
conda 23.3.1
```

Now, you are ready to go!

## VSCode 101

(You may skip this section if you are already familiar with VSCode.)

Once you have installed Anaconda, you can use any text editor to write Python code. However, it is recommended that you use [VSCode](https://code.visualstudio.com/) for this class. 

![VSCode](assets\vscode.png)

To install VSCode, go to the [VSCode website](https://code.visualstudio.com/) and download the installer for your operating system. Then, run the installer and follow the instructions.

Once you have installed VSCode, you can open it and start using it. However, you will need to install some extensions to make it work with Python. To do this, click on the Extensions icon on the left side of the window. Then, search for the `Python` extension and install it.

![VSCode Extensions](assets\extension.png)

There are also other extensions that you might find useful. For example, you might want to install the `Code Runner` extension to run your code directly from VSCode. 


## Python Basics

### Hello World

Let's start with a simple example. Open VSCode and create a new file called `hello.py`. Then, type the following code in the file:

```python
print("Hello World!")
```

Then, save the file and run it. You should see the following output:

```
Hello World!
```

### Strings

In Python, strings are sequences of characters enclosed in single or double quotes. It may also be enclosed in triple quotes. For example, the following are all valid strings:

```python
"Hello World!"
'Hello World!'
"""Hello World!"""
```

You can also use the `+` operator to concatenate strings. For example:

```python
"Hello" + " " + "World!"
```

You can also use the `*` operator to repeat a string. For example:

```python
"Hello" * 3
```

`f-strings` are a special type of string that allows you to insert variables into a string. It is commonly used to format strings and will be used extensively in this tutorial later on and in the rest of the course. For example:

```python
name = "John"
f"Hello {name}!"
```

### Numbers

In Python, there are two types of numbers: integers and floats. Integers are whole numbers, while floats are numbers with a decimal point. For example, the following are all valid numbers:

```python
print(f"1 is an integer: {type(1)}")
print(f"1.0 is a float: {type(1.0)}")
print(f"1.00000 is also a float: {type(1.00)}")
```

When concatenating strings and numbers, you need to convert the numbers to strings first. For example:

```python
print("The number is " + str(1))
```

Or, you can use f-strings:

```python
print(f"The number is {1}")
```

You can also specify the number of decimal places when printing floats:

```python
print(f"The number is {3.73373373:.2f}")
```

### Booleans

Booleans are either `True` or `False`. They are used to represent the truth value of a statement. For example:

```python
print(f"True is a boolean: {type(True)}")
print(f"False is also a boolean: {type(False)}")
```

You can also use the `and`, `or`, and `not` operators to combine booleans. For example:

```python
print(True and False)
print(True or False)
print(not True)
```

### Lists

Lists are ordered collections of items. They are enclosed in square brackets and separated by commas. For example:

```python
[1, 2, 3]
["a", "b", "c"]
[1, "a", True]
```

You can access items in a list using their index. For example:

```python
l = [1, 2, 3, 4, 5, 6, 7]
print(l[0])
print(l[1])
print(l[2])
print(l[-1])
print(l[-2])
print(l[0:2])
print(l[1:])
print(l[:2])
```

Lists are mutable, which means that you can change their values. For example:

```python
l = [1, 2, 3]
l[0] = 4
print(l)
```

There are also many functions that you can use to manipulate lists. For example:

```python
l = [1, 2, 3]
l.append(4)
print(l)
l.insert(0, 0)
print(l)
l.pop()
print(l)
l.remove(2)
print(l)
```

Here are some other useful functions:

```python
l = [5, 2, 7, 1, 3, 9, 4, 6, 8]
print(len(l))
print(min(l))
print(max(l))
print(sum(l))
print(sorted(l))
print(sorted(l, reverse=True))
```

Note that the `sorted` function returns a new list, while the `sort` method sorts the list in-place and returns `None`. For example:

```python
l = [5, 2, 7, 1, 3, 9, 4, 6, 8]
print(l.sort())
print(l)
```

You can also use the `+` operator to concatenate lists. For example:

```python
[1, 2, 3] + [4, 5, 6]
```

### Tuples

Tuples are ordered collections of items. They are enclosed in parentheses and separated by commas. They are similar to lists, except that they are immutable. For example:

```python
print( (1, 2, 3) )
print( ("a", "b", "c") )
print( (1, "a", True) )
```

```python
t = (1, 2, 3)
print(t[0])
t[0] = 4
```

### Sets

Sets are unordered collections of unique items. They are enclosed in curly braces and separated by commas. For example:

```python
print(    {1, 2, 3, 3, 3, 3, 3, 3, 3}    )
print(    {"a", "b", "c", "a"}    )
print(    {1, "a", True, False, True}    )
```

You can also use the `in` operator to check if an item is in a set. This can also be used with lists and tuples. For example:

```python
s = {1, 2, 3}
print(1 in s)
print(4 in s)
```

To add items to a set, you can use the `add` method or the `update` method. For example:

```python
s = {1, 2, 3}
s.add(4)
print(s)
s.update([5, 6, 7])
print(s)
```

### Dictionaries

Dictionaries are unordered collections of key-value pairs. They are enclosed in curly braces and separated by commas. An similar data structure in other languages is called a map, such as hash maps in Java. For example:


```python
print(    {"a": 1, "b": 2, "c": 3}    )
print(    {1: "a", 2: "b", 3: "c"}    )
print(    {1: 1, "a": "a", True: True}    )
```

Dictionaries are mutable, which means that you can change their values. For example:

```python
d = {"a": 1, "b": 2, "c": 3}
d["a"] = 4
print(d)
```

You can also use the `in` operator to check if a key is in a dictionary. For example:


```python
d = {"a": 1, "b": 2, "c": 3}
print("a" in d)
print("c" in d.keys())
print(1 in d)
```

To check if a value is in a dictionary, you can use the `values` method. For example:

```python
d = {"a": 1, "b": 2, "c": 3}
print(1 in d.values())
print("a" in d.values())
```

To add items to a dictionary, you can use the `update` method. You can also use the way similar to accessing items in a list. For example:

```python
d = {"a": 1, "b": 2, "c": 3}
d.update({"d": 4})
print(d)
d["e"] = 5
print(d)
```

### Conditionals

You can use the `if`, `elif`, and `else` keywords to write conditional statements. For example:

```python
if 1 < 2:
    print("1 is less than 2")
elif 1 > 2:
    print("1 is greater than 2")
else:
    print("1 is equal to 2")
```

You can also use the `and`, `or`, and `not` operators to combine conditions. For example:

```python
if 1 < 2 and 2 < 3:
    print("1 is less than 2 and 2 is less than 3")
if 1 < 2 or 1 > 2:
    print("1 is less than 2 or 1 is greater than 2")
if not 1 > 2:
    print("1 is not greater than 2")
if 1 == 2:
    print("1 is equal to 2")
```

Python also supports the ternary operator. For example:

```python
print("1 is not equal to 2") if 1 != 2 else print("1 is equal to 2")
```

### Loops

You can use the `for` and `while` keywords to write loops. For example:

```python
for i in range(5):
    print(f"For loop iteration {i}")
    while i < 3:
        print(f"While loop iteration {i}")
        i += 1
```

You can also use the `break` and `continue` keywords to control the flow of loops. For example:

```python
for i in range(5):
    if i == 2:
        break
    print(f"For loop iteration {i}")
    while i < 3:
        i += 1
        if i == 2:
            continue
        print(f"While loop iteration {i}")
```

### Functions

You can use the `def` keyword to define functions. For example:

```python
def add(a, b):
    return a + b

print(add(1, 2))
```

You can also use the `lambda` keyword to define anonymous functions. For example:

```python
add = lambda a, b: a + b
print(add(1, 2))
```

In this class, we will be using Type Hints to specify the types of function parameters and return values. For example:

```python
from typing import Tuple
def mystery_function(a: int, b: int, c: Tuple[int, int]) -> int:
    return a + b + c[0] + c[1]

mystery_function(1, 2, (3, 4))
```

Type hints are not required nor enforced by Python but are meant help you understand the code better. For example, the function signature below means that the function `mystery_function` takes two integers `a` and `b` and a tuple of two integers as input and returns an integer.

We also use docstrings and doctests to document functions. For example:


```python
def mystery_function(a: int, b: int, c: Tuple[int, int]) -> int:
    """
    This is a docstring. It is used to describe the function.

    Below are some examples of doctests.
    >>> mystery_function(1, 2, (3, 4))
    10

    >>> mystery_function(1, 2, (3, 4, 5)) # This works but does not follow the type hints.
    10

    >>> mystery_function(1, 2) # This would cause an error.
    Traceback (most recent call last):
        ...
    TypeError: mystery_function() missing 1 required positional argument: 'c'
    """

    return a + b + c[0] + c[1]
```

A docstring is a string that is the first statement in a function. It is used to describe the function. Inside the docstring, you can write doctests. Doctests are examples of how to use the function. They are written in the form of a Python interactive session. In our class, doctests are used as your local tests (public tests). They are part of the test cases that we use to grade your assignments. You can run the doctests by running the following command in the terminal:

```bash
python -m doctest -v file.py
```

In most cases, we have programmed the doctests for you in a way that you can test your implementation by running the Python file directly, and you will see whether you passed the doctests or not. For example:

```bash
python file.py
```

```
All tests passed!
```

### Classes

Python can be used as an object-oriented programming language. You can use the `class` keyword to define classes. For example:

```python
class CS373:
    def __init__(self, name):
        self.name = name

    def get_name(self):
        return self.name

    def set_name(self, name):
        self.name = name
```

Here, `__init__` is the constructor of the class. It is called when you create an instance of the class. For example:

```python
cs373 = CS373("CS373")
print(cs373.get_name())
cs373.set_name("CS37300")
print(cs373.get_name())
```

While Python does have access modifiers, similar to `private` in Java, we will not be using them in this class. This means that you can access any attribute or method of a class directly without the need for getters and setters. For example:

```python
cs373 = CS373("CS373")
print(cs373.name)
cs373.name = "CS37300"
print(cs373.name)
```

### Modules

You can use the `import` keyword to import modules. For example:

```python
import math
print(math.sqrt(4))
```

You can also use the `from` keyword to import specific functions from a module. For example:

```python
from math import sqrt
print(sqrt(4))
```

You can also use the `as` keyword to rename a module. For example:

```python
import math as magic
print(magic.sqrt(4))

from math import sqrt as magic
print(magic(4))
```

### Exceptions

Exceptions are similar to errors in Java. You can use the `try`, `except`, and `finally` keywords to handle exceptions. While we do not expect you to use exceptions in your assignments, you should be familiar with them as you will see them in the code that we provide you. For example:

```python
try:
    print(1 / 0)
except ZeroDivisionError:
    print("Cannot divide by zero")
finally:
    print("This will always be printed")
```

### Truthiness

In Python, the following values are considered false:

- `None`
- `False`
- `0`
- `0.0`
- `0j`
- `Decimal(0)`
- `Fraction(0, 1)`
- `[]` (an empty list)
- `{}` (an empty dict)
- `()` (an empty tuple)
- `''` (an empty str)
- `b''` (an empty bytes)
- `set()` (an empty set)
- an empty range, like `range(0)`
- objects for which
    - `obj.__bool__()` returns `False`
    - `obj.__len__()` returns `0`
- etc.

All other values are considered true, including some cases such as:

- `[0]`
- `"0"`
- `"False"`
- `()`

### Type Casting

You can use the following functions to cast between types:

- `int()`
- `float()`
- `str()`
- `bool()`
- `list()`
- `tuple()`
- `set()`
- `dict()`

For example:

```python
print(int("1"))
print(float("1"))
print(str(1))
print(bool(1))
print(list((1, 2, 3)))
print(tuple([1, 2, 3]))
print(set([1, 2, 3]))
print(dict([(1, 2), (3, 4)]))
```

