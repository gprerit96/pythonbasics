---
layout: default
title: Introduction to Python Part 2
nav_order: 99
---

# Introduction to Python Part 2: Common Packages

## Introduction

In this tutorial, we will cover some of the most common packages used in Python and our course. We will be using some of the techniques we learned in the previous tutorial, so make sure you have understood the previous tutorial before moving on to this one.

While we will try to cover as many packages shown in our programming assignments, we will not be able to cover all of them. However, the packages we will cover in this tutorial will be enough to get you started on your programming assignments.

## Built-in Packages

### `math` and its variants

The `math` package is a built-in package that contains many useful mathematical functions. To use the `math` package, we need to import it first.

```python
import math
```

The `math` package contains many useful functions, such as `math.sqrt()` for square root, `math.sin()` for sine, `math.cos()` for cosine, `math.log()` for logarithm, and `math.exp()` for exponential. For example, to calculate a logarithm of 4 with base 2, we can use the following code.

```python
import math
print(f"Logarithm of 4 with base 2 is {math.log(4, 2)}")
print(f"Alternatively, we can use the log2 function: {math.log2(4)}")
```

The `math` package also contains some useful constants, such as `math.pi` for $\pi$ and `math.e` for $e$. For example, to calculate the area of a circle with radius 2, we can use the following code.

```python
import math
print(f"Area of a circle with radius 2 is {math.pi * 2 ** 2}")
```

Note that typically, `math` functions only work with numbers. If you want to use them with arrays, you need to use `numpy` instead:

```python
import numpy as np
r = np.array([1, 2, 3])
print(f"Area of a circle with radius {r} is {np.pi * r ** 2}")
```

### `random`

The `random` package is a built-in package that contains many useful functions for random number generation. To use the `random` package, we need to import it first.

```python
import random
```

The `random` package contains many useful functions, such as `random.random()` for generating a random number between 0 and 1, `random.randint()` for generating a random integer between two numbers, `random.choice()` for randomly choosing an element from a list, and `random.shuffle()` for randomly shuffling a list. For example, to generate a random number between 0 and 1, we can use the following code.

```python
import random
print(f"A random number between 0 and 1 is {random.random()}")
```

To generate a random integer between 1 and 10, we can use the following code.

```python
import random
print(f"A random integer between 1 and 10 is {random.randint(1, 10)}")
```

To randomly choose an element from a list, we can use the following code.

```python
import random
print(f"A random element from [1, 2, 3] is {random.choice([1, 2, 3])}")
```

To randomly shuffle a list, we can use the following code.

```python
import random
l = [1, 2, 3]
random.shuffle(l)
print(f"A random shuffle of [1, 2, 3] is {l}")
```

While the `random` package is very useful for generating random numbers, it is not very useful for generating random numbers for machine learning. In come cases, we need to generate random numbers with a specific distribution, such as a normal distribution. In these cases, we need to use the `numpy` package instead:

```python
import numpy as np
print(f"A random number from a normal distribution is {np.random.normal()}")
```

As many of you might have already known, computer-generated random numbers are not truly random. They are generated using a pseudo-random number generator (PRNG). The PRNG is initialized with a seed, and it will generate a sequence of numbers that looks random. However, if we initialize the PRNG with the same seed, it will generate the same sequence of numbers. This is useful for debugging, as we can set the seed to a fixed value to make sure that the program will always generate the same sequence of random numbers. To set the seed, we can use the following code.

```python
import random
random.seed(0)
print(f"A random number between 0 and 1 is {random.random()}")

import numpy as np
np.random.seed(0)
print(f"A random number from a normal distribution is {np.random.normal()}")
```

According to Python and `numpy` documentation, with the same seed, the same sequence of random numbers will be generated on all systems. However, `numpy` removed backward compatibility for `numpy.random` in a recent update, so the same sequence of random numbers might not be guaranteed across different versions of `numpy`.

### `datetime`

The `datetime` package is a built-in package that contains many useful functions for date and time. To use the `datetime` package, we need to import it first.

```python
import datetime
```

The `datetime` package contains many useful functions, such as `datetime.datetime.now()` for getting the current date and time, `datetime.datetime.strptime()` for parsing a string into a date and time, and `datetime.datetime.strftime()` for formatting a date and time into a string. For example, to get the current date and time, we can use the following code.

```python
import datetime
print(f"The current date and time is {datetime.datetime.now()}")
print(f"The current date and time in a more readable format is {datetime.datetime.now().strftime('%Y-%m-%d %H:%M:%S')}")
```

To parse a string into a date and time, we can use the following code.

```python
import datetime
print(f"September 28, 2001 is {datetime.datetime.strptime('2001-09-28', '%Y-%m-%d')}")
```

### `sys`

The `sys` package is a built-in package that contains many useful functions for system-related operations. To use the `sys` package, we need to import it first.

```python
import sys
```

The `sys` package contains many useful functions, such as `sys.argv` for getting the command-line arguments, `sys.exit()` for exiting the program, and `sys.stdin` and `sys.stdout` for reading from and writing to the standard input and output. For example, to get the command-line arguments, we can use the following code.

```python
import sys
print(f"The command-line arguments are {sys.argv}")
```

To exit the program, we can use the following code. Do NOT use this code in Jupyter Notebook, as it will exit the kernel. Also, do NOT use this in your assignment, as it will cause the autograder to fail.

```python
import sys
sys.exit()
```

To read from the standard input, we can use the following code. Though, we can use the `input()` function instead.

```python
import sys
print("Please enter your first name: ")
first = sys.stdin.readline()
last = input("Please enter your last name: ")
print(f"Hello, {first} {last}!")
```

### `os`

The `os` package is a built-in package that contains many useful functions for operating system-related operations. To use the `os` package, we need to import it first.

```python
import os
```

The `os` package contains many useful functions, such as `os.getcwd()` for getting the current working directory, `os.chdir()` for changing the current working directory, `os.listdir()` for listing the files in a directory, `os.mkdir()` for creating a directory, `os.rmdir()` for removing a directory, `os.remove()` for removing a file, and `os.path.exists()` for checking if a file or directory exists.

In our programming assignments, we will use `os.system()` to run a command in the terminal. For example, to run `ls` in the terminal, we can use the following code.

```python
import os
os.system("ls")
```

To get the path of a dataset file in the same folder as the current file, we can use the following code.

```python
import os
print(f"The path of the dataset file is {os.path.join(os.path.dirname(__file__), 'dataset.csv')}")
```

However, in Jupyter Notebook, `__file__` is not defined, so if you want to use the same code in both Jupyter Notebook, you may change to the following code instead.

```python
import os
print(f"The path of the dataset file is {os.path.join(os.getcwd(), 'dataset.csv')}")
```

### `collections`

The `collections` package is a built-in package that contains many useful functions for collections. To use the `collections` package, we need to import it first.

```python
import collections
```

The `collections` package contains many useful functions, such as `collections.Counter()` for counting the number of occurrences of each element in a list, `collections.defaultdict()` for creating a dictionary with a default value, and `collections.OrderedDict()` for creating a dictionary that remembers the order of insertion. For example, to count the number of occurrences of each element in a list, we can use the following code.

```python





