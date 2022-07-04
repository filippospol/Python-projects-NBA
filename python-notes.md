# Introduction to Python 

### Introduction

This notebook contains information on Python programming language.
Python is an object-oriented programming language. Every item in Python is considered an **OBJECT**. Objects have identifiable **CLASSES** (i.e., data types).
Depending on an object's class, it carries some things with it. 
These things can be accessed through Pythons dot syntax: ```object.method()```
A function attached to an object is called a **METHOD**, whereas every other non-function thing attached is called an **ATTRIBUTE**.

### Variable assignment

Variables serve as reference points to an object. Using the syntax ```variable_name = value```, users can enter a value in Python's memory.  
Mathematical symbols and calculations include:  

| Calculation | Symbol |
| :- | --- |
| addition | + |
| subtraction | - |
| multiplication | * |
| division | / |
| exponent | ** |
| floor division | // |
| modulus | % |


```python
# create two variables
x = 3
y = 4
# simple calculations between two numbers
print(x+y)
```

    7
    


```python
print(x-y)
```

    -1
    


```python
print(x*y)
```

    12
    


```python
print(x/y)
```

    0.75
    


```python
print(x**y)
```

    81
    

### Functions

A function is defined as a block or code, that runs only when it is called. Information can be passed inside a function's *argument(s)*. Arguments are entered after the function's name, inside parentheses. Note that a function can have zero arguments.  
After stating the function name and argument(s), there are two other components.  
- **docstring**: text inside triple quotes, briefly indicating what the function does.  
- **body**: block of code to be run.  

Below is the function syntax:  


```python
# def function_name(arg(s))
#   '''
#   function docstring
#   '''
#   function_body
```


```python
# example of function:
def add_three(x):
    '''This function takes a number and adds 3.'''
    y = x + 3
    return(y)
z = add_three(124)
print(z)
```

    127
    

### Booleans

Boolean is a binary data type that takes either one of two options: ```True``` or ```False```. It is usually a result of a comparison between two values. Such comparisons can be done using several operators:  

| Operation | Symbol |
| :- | --- |
| greater than | > |
| less than | < |
| equal | == |
| not equal | != |
| geq | >= |
| leq | <= |  

Some extra operators include ```and```, ```or``` and ```not```. Furthermore, booleans can be converted to other data types:  
- all numbers are treated as True, except 0.  
- all strings are treated as True, except an empty string.

### Conditional statements

Booleans and logical operators come in handy when we want to use conditional statements, i.e. ```if``` loops.


```python
# if (condition1):
#     code_block1
# elif (condition2):
#     code_block2
# else:
#     code_block3
```


```python
# simple function using booleans and if loop
def evalplayer(x):
    '''
    This function evaluates a player as a scorer, given his points/game average.
    '''
    if x > 25:
        return("Top scorer")
    elif x > 17.5:
        return("Good scorer")
    else:
        return("Average scorer")
print(evalplayer(38))
```

    Top scorer
    

### Lists

Lists are data types that represent ordered sequences of values. It is similar to arrays or vectors in other programming languages. Python implements *zero-based indexing*,  meaning that the first item in a list is in position 0! <br>
List items are ordered, changeable, and allow duplicate values. Additionally, lists can contain different data types.


```python
players = ["Jayson Tatum", "Jaylen Brown", "Marcus Smart", "Al Horford"]
pts = [26.9, 23.6, 12.1, 10.2]
```


```python
print(players)
```

    ['Jayson Tatum', 'Jaylen Brown', 'Marcus Smart', 'Al Horford']
    

#### Slicing lists

One useful aspect is what is called *slicing*. Users have the ability to extract list items:


```python
print(pts[0])      # first item of list
```

    26.9
    


```python
print(pts[-1])     # last item of list
```

    10.2
    


```python
print(pts[:2])     # first 2 items
```

    [26.9, 23.6]
    


```python
print(pts[-3:])    # last 3 items
```

    [23.6, 12.1, 10.2]
    

#### Modifying lists

Another feature is the modification of list items, i.e. editing already-existing values:


```python
players[3] = "Derrick White"
```


```python
print(players)
```

    ['Jayson Tatum', 'Jaylen Brown', 'Marcus Smart', 'Derrick White']
    

#### List functions/methods

By using the object-oriented syntax mentioned in the **Introduction**, we can access all the methods and attributes of a list:


```python
len(players) # length of list
```




    4




```python
sorted(pts, reverse=True) # sorted version of a list. reverse=False is the default
```




    [26.9, 23.6, 12.1, 10.2]




```python
players.remove("Derrick White") # remove an item
```


```python
players
```




    ['Jayson Tatum', 'Jaylen Brown', 'Marcus Smart']




```python
players.append("Nik Stauskas") # add an item
```


```python
players
```




    ['Jayson Tatum', 'Jaylen Brown', 'Marcus Smart', 'Nik Stauskas']




```python
players.pop() # remove and print last item
```




    'Nik Stauskas'




```python
players.index("Jayson Tatum") # locate index of a given value
```




    0




```python
# players.clear() # empty a list
```


```python
"Stephen Curry" in players # is a given value in the list?
```




    False



Other list methods include ```extend```, ```copy```, ```reverse```, ```sort``` etc.


```python
# list of lists
x= [[1,2,3],[4,5,6]]
# return the last item of the first list
print(x[0][-1])                  
```

    3
    

### Tuples

A tuple is a data type which is very similar to a list, but with two major differences:  
- Tuples are defined using parentheses, instead of square brackets.  
- Tuples cannot be modified (immutable) and do not share attributes/methods with lists!


```python
mvp = ("Giannis Antetokounmpo", "Joel Embiid", "Nikola Jokic")
mvp.pop()  # error
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    ~\AppData\Local\Temp/ipykernel_16744/2248049845.py in <module>
          1 mvp = ("Giannis Antetokounmpo", "Joel Embiid", "Nikola Jokic")
    ----> 2 mvp.pop()  # can't be done
    

    AttributeError: 'tuple' object has no attribute 'pop'


### Loops

Loops are used in programming to repeatedly run blocks of code. There are two types of iterative loops:  
- A **for** loop is used to iterate over a known sequence. This sequence can be alist, tuple, dictionary, set, or string.  
- A **while** loop is used to iterate until a certain condition is met. When the condition becomes ```False```, the iteration stops.


```python
for i in players:
    print(i, end = "\n") # list items, one item per row
```

    Jayson Tatum
    Jaylen Brown
    Marcus Smart
    


```python
for i in players[0]:
    print(i, end = " ") # print all characters of a string
```

    J a y s o n   T a t u m 


```python
for i in players[2]:
    if i == "a":
        continue
    print(i, end = " ") # skip an iteration for a given condition
```

    M r c u s   S m r t 


```python
for i in players[2]:
    if i == "c":
        break
    print(i, end = " ") # stop the loop for a given condition
```

    M a r 


```python
for i in range(10):
    print(i, end = " ") # range(x) gives a sequence of numbers from 0 to x-1
```

    0 1 2 3 4 5 6 7 8 9 


```python
# for i in range(2,17):
    print(i, end = " ") # range(x,y) gives a sequence of numbers from x to y-1
```

### List comprehensions

List comprehensions are a very useful tool, as they offer a shorter syntax when users want to create a new list coming from an existing list. Instead of using a for loop, a list comprehension is the one-line equivalent:


```python
print(pts)
```

    [26.9, 23.6, 12.1, 10.2]
    


```python
 # create an empty list
root_pts = []
```


```python
# fill the list using iterative loop
for i in pts:
    root_pts.append(round(i**(1/2),2))
print(root_pts)
```

    [5.19, 4.86, 3.48, 3.19]
    


```python
# do the same with a list comprehension
print([round(i**(1/2),2) for i in pts])
```

    [5.19, 4.86, 3.48, 3.19]
    

The general structure of a list comprehension can be found below:
for (set of values to iterate):
  if (conditional filtering): 
    output_expression()
    
# you can do the above in one line!

[ output_expression() for set of values to iterate if (conditional filtering) ]
<br>


```python
# Other examples

# find all numbers from 1 to 1000 that are divisible by 7
# [i for i in range(1,1000) if i % 7 == 0]

# find all numbers from 1 to 1000 that include 3
# [i for i in range(1,1000) if "3" in str(i)]

# count the number of spaces in a string
# len([i for i in "Hello friend" if i == " "])
```

### Strings

String is a data type, denoting everything that is contained in single or double quotes. Strings can be used as sequences, but are immutable.


```python
print(players)
```

    ['Jayson Tatum', 'Jaylen Brown', 'Marcus Smart']
    


```python
print(type(players[0])) 
```

    <class 'str'>
    

String manipulation is an essential tool that data scientists must have in their arsenal. Python's string methods help us do this. For a given string *s*, here are the most commonly used methods & operations:

- ```s.lower()```, ```s.upper()```, ```s.title()``` and ```s.islower()```, ```s.isupper()```, ```s.istitle()``` convert or check if a string is lower / upper / title case.  
- ``` s2 in s``` checks if a string s2 is contained in string s.  
- ```s.strip()``` removes all the whitespaces from string s.  
- ```s.find(s2)``` finds and returns the lowest index of s2 in s.  
- ```s.replace(s2,s3,count=1)``` finds s2 in s and replaces the first occurence with s3.  
- ```s.startswith(s2)``` and ```s.endswith(s2)``` return true if string s starts / ends with string s2.  
- ```s.split()``` splits string s on separate components that are between whitespaces. Returns a list.  
- ```s.lstrip()``` and ```s.rstrip()``` remove leading / trailing whitespaces from a string s.  
- ```s + s2 + s3``` concats several string variables.

Below are some examples for string manipulation:


```python
"{a} averaged {b} PPG in the regular season".format(a=players[0],b=pts[0])
```




    'Jayson Tatum averaged 26.9 PPG in the regular season'




```python
[i.upper() for i in players]
```




    ['JAYSON TATUM', 'JAYLEN BROWN', 'MARCUS SMART']




```python
["J" in i for i in players]
```




    [True, True, False]




```python
[i.replace("a","x") for i in players]
```




    ['Jxyson Txtum', 'Jxylen Brown', 'Mxrcus Smxrt']



### Dictionaries

Dictionaries are a built-in Python data structure for mapping keys to values. No duplicate keys are allowed. Dictionaries are created using curly brackets. The main difference to lists is that keys can take any possible and unordered value.


```python
{1:players[0], 2:players[1], 3:players[2]}
```




    {1: 'Jayson Tatum', 2: 'Jaylen Brown', 3: 'Marcus Smart'}




```python
type({1:players[0], 2:players[1], 3:players[2]})
```




    dict



### Modules

Modules refer to a ```.py``` file containing Python statements and definitions. More importantly, modules can contain custom functions, which are not built-in a priori. All users can create modules and make them available online. 

### Libraries

Up until now, we have only presented built-in functions and attributes of Python. In the case users want to use more specific algorithms and techniques, there is a great variety of custom libraries. A Python **library** is a collection of modules that contain functions and classes that can be used by other programs to perform various tasks. Some of these libraries are in the "standard library", meaning you can find them anywhere you run Python. Other libraries can be easily added, even if they don't always come with Python. We can access these blocks of code using **imports**.


```python
import math

print("It's math! It has type {}".format(type(math)))
```

    It's math! It has type <class 'module'>
    


```python
# we can also import a module using a different, easier alias:
# import math as mt
```


```python
# dir() retuns a library's/module's components. This can be variables or functions:
print(dir(math), sep=" ")
```

    ['__doc__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'comb', 'copysign', 'cos', 'cosh', 'degrees', 'dist', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'isqrt', 'lcm', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'nextafter', 'perm', 'pi', 'pow', 'prod', 'radians', 'remainder', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc', 'ulp']
    


```python
# some components of the `math` module:
print(round(math.pi,5))
```

    3.14159
    


```python
# log(value, base)
print(math.log(30, math.e))
```

    3.4011973816621555
    


```python
# stop using the object syntax `module.component` by importing everything from a module:
from math import *
```


```python
print(round(pi,5), log(30,e))
```

    3.14159 3.4011973816621555
    

The main disadvantage with the star imports is the fact that it is highly likely that two packages have some items with the same name. One way to overcome this is to load only the things we will need from each module.


```python
# from math import log, pi
# from numpy import asarray
```

To conclude, every time you get stuck, there are three ways to get further information on strange objects:  
- ```type()```  
- ```dir()```  
- ```help()```
