---
title : Python Cheat Sheet
category : Cheat Sheets
author : Makoto Yaguchi
---

# Python Cheat Sheet
[Python Cheat Sheet](https://www.pythoncheatsheet.org/modules/itertools-module)

[TOC]

## Accessing help and getting object types
```Python
import pa1 + 1 # Everything after the hash symbol is ignored by Python
help(max) # Display the documentation for the max function
type('a') # Get the type of an object — this returns str
```

## Importing packages
```Python
import pandas
import numpy as np
import matplotlib.pyplot as plt
from dirName.fileName import function 
```

## The working directory
```Python
import os
os.getcwd()
os.chdir(‘new/working/directory’)
os.path.basename(__file__)
os.path.dirname(__file__)
```

## Math Operators
### Arithmetic operators
```Python
102 + 37 # Add two numbers with +
102 - 37 # Subtract a number with -
4 * 6    # Multiply two numbers with *
22 / 7   # Divide a number by another with /
22 // 7  # Integer divide a number with //
3 ** 4   # Raise to the power with **
22 % 7   # Returns 1 # Get the remainder  after division with %
```

### Assignment operators
```Python
a = 5    # Assign a value to a
x[0] =1  # Change the value of an item in a list
var += 1 # var = var + 1
var -= 1 # var = var - 1
var *= 1 # var = var * 1
var /= 1 # var = var / 1
var %= 1 # var = var % 1
```

### Numeric comparison operators
```Python
3 == 3  # Test for equality with ==
3 != 3  # Test for inequality with !=
3 > 1   # Test greater than with >
3 >= 3  # Test greater than or equal to with >=
3 < 4   # Test less than with <
3 <= 4  # Test less than or equal to with <=
```

### Logical operators
```Python
~(2 == 2)          # Logical NOT with ~
(1 != 1) & (1 < 1) # Logical AND with &
(1 >= 1) | (1 < 1) # Logical OR with |
(1 != 1) ^ (1 < 1) # Logical XOR with ^
```

## Geting started with lists
### Createing lists
```Python
x = [1, 3, 2]
x = [i for i in range(1, 4)]
```

### List functions and mathods
```Python
sorted(x)   # Returns [1, 2, 3]
reversed(x) # Returns [2, 3, 1]
# list in-place (replaces x)
x.sort() # Returns None
x.reversed() # Returns None
# Count the number of element 2 in the list
x.count(2)
```

### Selecting list elements
```Python
x = ['a', 'b', 'c', 'd', 'e']
x[0]    # 'a'
x[-1]   # 'e'
x[1:3]  # ['b', 'c']
x[2:]   # ['c', 'd', 'e']
x[:3]   # ['a', 'b', 'c']
```

### Concatenating lists
```Python
x, y = [1, 3, 6], [10, 15, 21]
x + y # [1, 3, 6, 10, 15, 21]
3 * x # [1, 3, 6, 1, 3, 6, 1, 3, 6]
```

## Getting started with dictionaries
### Creating dictionaries
```Python
{'a': 1, 'b': 4, 'c': 9}
L, N = ['a', 'b', 'c'], [1, 4, 9]
{l : n for l, n in zip(L, N)} # {'a': 1, 'b': 4, 'c': 9}
```

### Dictionary functions and methods
```Python
a = {'a': 1, 'b': 2, 'c': 3}
x.keys() # dict_keys(['a', 'b', 'c'])
x.values() # dict_values([1, 2, 3])
x['a'] # 1
```

## Numpy arrays
### Creating arrays
```Python
np.array([1, 2, 3])     # array([1, 2, 3])
np.arange(1, 5)         # array([1, 2, 3, 4])
np.arange(1, 5, 2)      # array([1, 3])
np.repeat([1, 3, 6], 3) # array([1, 1, 1, 3, 3, 3, 6, 6, 6])
np.tile([1, 3, 6], 3)   # array([1, 3, 6, 1, 3, 6, 1, 3, 6])
```

### Math functions and methods
```Python
np.log(x)         # logarithm of an array
np.exp(x)         # exponential of an array
np.max(x)         # Get maximum value of an array
np.min(x)         # Get minimum value of an array
np.sum(x)         # sum of an array
np.mean(x)        # mean of an array
np.quantile(x, q) # q-th quantile of an array x
np.round(x, n)    # Round an array to n decimal places
np.var(x)         # variance of an array
np.std(x)         # standard deviation of an array
```

## Getting started with characters and strings
```Python
strings = "DataCamp"
'He said, "DataCamp"'
"""
A Frame of Data
Tidy, Mine, Analyze It
"""
strings[0]   # 'D'
strings[0:2] # 'Da'
```

### Combining and splitting strings
```Python
"Data" + "Framed"       # 'DataFramed'
3 * "data "             # 'data data data '
"beekeepers".split("e") # ['b', '', 'k', '', 'p', 'rs']
```

### Mutate strings
```Python
str = "Jack and Jill"
str.upper()           # 'JACK AND JILL'
str.lower()           # 'jack and jill'
str.title()           # 'Jack And Jill' 
str.replace("J", "P") # 'Pack and Pill'
```

## Getting stated with DataFrames
### Creating DataFrames
```Python
pd.DataFrame(
    [[ 0,  1,  2,  3], [ 4,  5,  6,  7], [ 8,  9, 10, 11]],
    columns=['col_0', 'col_1', 'col_2', 'col_3'],
    index=['row_0', 'row_1', 'row_2']
)
pd.DataFrame({
    'a': [1, 2, 3],
    'b': np.array([4, 4, 6]),
    'c': ['x', 'x', 'y']
})
pd.DataFrame([
    {'a': 1, 'b': 4, 'c': 'x'},
    {'a': 1, 'b': 4, 'c': 'x'},
    {'a': 3, 'b': 6, 'c': 'y'}
])
```

### Selecting DataFrame Elements
```PYthon
df.iloc[2]             # Select the 4th row
df['col_0']            # Select one column by name
df[['col_1', 'col_2']] # Select multiple columns by names
df.iloc[:, 2]          # Select 3rd column
df.iloc[2, 2]          # Select the element in the 3th row, 3rd column
```

### Munipulating DataFrames
```PYthon
pd.concat([df, df])                 # Concatenate DataFrames vertically
pd.concat([df, df], axis="columns") # Concatenate DataFrames horizontally
df.query('logical_condition')       # Get rows matching a condition
df.drop(columns=['col_name'])       # Drop columns by name
df.rename(columns={"oldname": "newname"})   # Rename columns 
df.assign(temp_f=9 / 5 * df['temp_c'] + 32) # Add a new column
df.mean()                     # Calculate the mean of each column
df.agg(aggregation_function)  # Get summary statistics by column
df.drop_duplicates()          # Get unique rows
df.sort_values(by='col_name') # Sort by values in a column in ascending order
df.nlargest(n, 'col_name')    # Get the rows with the n largest values of a column
```

## Datetime Module
### datetime
```Python
from datetime import datetime
datetime.datetime(year, month, day, hour, minute, second)
obj = datetime(2024, 12, 1, 15, 35, 59)
obj.year        # 2022
obj.month       # 12
obj.day         # 1
obj.hour        # 15
obj.second      # 59
obj.microsecond # 0
```

### now() and today()
```Python
now = datetime.now()
now.date()      # datetime.date(2022, 7, 23)
now.time()      # datetime.time(19, 56, 49, 589806)
now.year        # 2022
now.month       # 7
now.day         # 23
now.hour        # 19
now.minute      # 56
now.second      # 49
now.microsecond # 589806
```

### strftime()
```Python
now.strftime("%d-%b-%Y")            # '23-Jul-2022'
now.strftime("%d-%m-%Y")            # '23-07-2022'
now.strftime("%d-%b-%Y")            # '23-Jul-2022'
now.strftime("%d-%m-%Y")            # '23-07-2022'
now.strftime("%m/%d/%Y")            # '07/23/2022'
now.strftime("%b/%d/%Y - %H:%M:%S") # 'Jul/23/2022 - 20:31:19'
```

### strptime()
```Python
datetime_str = '12-Jul-2023'
datetime.strptime(datetime_str, '%d-%b-%Y')            # datetime.datetime(2023, 7, 12, 0, 0)
datetime_str = 'Jul/12/2023 - 14:38:37'
datetime.strptime(datetime_str, "%b/%d/%Y - %H:%M:%S") # datetime.datetime(2023, 7, 12, 14, 38, 37)
```

### timedelta()
```Python
date_1 = datetime.strptime('12-Jul-2023', '%d-%b-%Y')
date_2 = datetime.strptime('01-Jan-2024', '%d-%b-%Y')
difference = date_2 - date_1 # datetime.timedelta(days=173)
difference.days              # 173

now = datetime.now()                 # datetime.datetime(2022, 7, 23, 21, 25, 2, 341081)
now + timedelta(days=10, seconds=15) # datetime.datetime(2022, 8, 2, 21, 25, 17, 341081)
now - timedelta(days=10, seconds=15) # datetime.datetime(2022, 7, 13, 21, 59, 41, 100883)
```

###
```Python
```
