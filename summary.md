# Introduction to Python - Summary

Python: object-oriented programming, every object has a method: `object_name.method_name()`.

### Data types

-  int, float, bool, str, list [], tuple (), dict {}.  
- Every data type has its distinct methods (example: ```list_name.append()```, ```str_name.replace()``` etc.

### Functions


```python
def function_name(args):              # HEADER
    ``` docstring ```                 # DOCSTRING
    statement(s)                      # BODY
```

### Conditional statements - logical operators


```python
if (condition_1):
    statements_1
elif (condition_2):
    statements_2
else:
    statements_3
```

### Loops

- `for` loop: iterate over a known sequence.  
- `while` loop: iterate until a condition is met.


```python
# FOR
for x in sequence:
    statements
    
# WHILE
while condition:
    statements
```

### List comprehensions

- Generate a new list from an existing list:  



```python
[ output_expression() for set of values to iterate if (condition) ]
```

### Modules-Libraries

- `import math` imports a module, but every time we want to call one of its components it has to be in the object.method() syntax.

- `from math import *` imports all the module's components and we dont need the object.method() syntax. We just use method().

- `from math import pi, log` imports selected components of a module.

- When in doubt, use: `type()`, `dir()`, `help()`.
