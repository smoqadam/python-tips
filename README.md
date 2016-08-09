## Python tips

List of python tips

1. [Use the Python 3 print function in Python 2](#use-the-python-3-print-function-in-python-2)
1. [Reverse a string or list](#reverse-a-string-or-list)
1. [Reverse by custom step](#reverse-by-custom-step)
1. [List slice assignment](#list-slice-assignment)
1. [Copy a list](#copy-a-list)
1. [Create a list out of string](#create-a-list-out-of-string)
1. [Print elements of a list by unpacking (only Python 3)](#print-elements-of-a-list-by-unpacking-only-python-3)
1. [Check file or directory exists](#check-file-or-directory-exists)
1. [Call an external command](#call-an-external-command)
1. [Capture output from an external command](#capture-output-from-an-external-command)
1. [Ternary conditional operator](#ternary-conditional-operator)
1. [else in for loop](#else-in-for-loop)
1. [Print to file](#print-to-file)
1. [Writing to file](#writing-to-file)
1. [Reading from file](#reading-from-file)
1. [Iterating over lines in a file](#iterating-over-lines-in-a-file)
1. [Accessing attributes which start with underscores](#accessing-attributes-which-start-with-underscores)

#### Use the Python 3 print function in Python 2
```python
# For Python 2, using the print() function from Python 3 helps future compatibility.
# It also allows better syntax when printing to files, or changing the line ending.
from __future__ import print_function

print('Python', 'Tips', sep='-', end='')
```

```python
import sys
print('There was an error!', file=sys.stderr)
```

```python
with open(filename, 'w') as f:
    print('Python!', file=f)
```

#### Reverse a string or list
```python
my_list = ['a','b','c','d','e']
reverse_list = my_list[::-1]

my_string = "python"
print(my_string[::-1])
# output : nohtyp
```

#### Reverse by custom step
```python
my_list = [1,2,3,4,5,6]
reverse_list = my_list[::-2]
print(reverse_list)
# output : [6,4,2]
```

#### List slice assignment
```python
my_list = ['a','b','c','d','e']
my_list[3:] = ['x','y','z']
print(my_list)
# output : ['a', 'b', 'c', 'x', 'y', 'z']
```

#### Copy a List
```python
a = [1, 2, 3, 4]
''' Considered as one of the weirdest syntax to copy elements.'''
a_copy = a[:]

''' Another way of copying a list.'''
a_copy2 = list()
a_copy2.extend(a) # output a_copy2 = [1, 2, 3, 4]
```

#### Create a list out of string
```python
data = "abcd"
data_list2 = list(data)  # OutPut: data_list = ['a', 'b', 'c', 'd'] 
```

#### Print elements of a list by unpacking (only Python 3)
```python
my_list = [1, 2, 3, 4]
print(*my_list, sep='\t')   # Print elements of my_list separated by a tab
```

#### Check file or directory exists
`os.path.isfile` used only for files
```python
import os.path
os.path.isfile(filename) # True if file exists
os.path.isfile(dirname) # False if directory exists
```

`os.path.exists` used for both files and directories
```python
import os.path
os.path.exists(filename) # True if file exists
os.path.exists(dirname) #True if directory exists
```

`pathlib.Path` method (included in Python 3+, installable with pip for Python 2)
```python
from pathlib import Path
Path(filename).exists()
```

#### Call an external command
```python
from subprocess import call
call(['ls,'-l'])
```

#### Capture output from an external command
```python
from subprocess import check_output
output = check_output(['ls', '/usr/bin'])
```

You can also capture `stderr` at the same time.
```python
from subprocess import check_output, STDOUT, CalledProcessError
try:
    output = check_output(['ls', '/nonexistent'], stderr=STDOUT)
except CalledProcessError:
    print('Error: {}'.format(output.decode()))
else:
    print('Success: {}'.format(output.decode()))
```

#### Ternary conditional operator
```python
print('True' if True else 'False')
```

#### `else` in `for` loop
An `else` block is executed if the loop body is not terminated by a `break` statement : 

```python
for i in range(5):
    print('Here we go!')
    if i == 2:
        break
else:
    print('There we went.')
# output : Here we go!
#          Here we go!
#          Here we go!
```
This `for` loop will get all the way to `else`:
```python
for i in range(5):
    print('Here we go!')
    if i == 10:
        break
else:
    print('There we went.')
# output : Here we go!
#          Here we go!
#          Here we go!
#          Here we go!
#          Here we go!
#          There we went.
```

#### Print to file

```python
# Using `with` and `open`, the file will be closed when the `with` block finishes.
with open(filename, 'w') as outputfile:
    print('Python!', file=outputfile)
```

#### Writing to file
```python
with open(filename, 'a') as outputfile:
    outputfile.write('Python!\n')
```

#### Reading from file
```python
with open('file.txt', 'r') as inputfile:
    data = inputfile.read()
```

#### Iterating over lines in a file
When iterating over lines in a file, this method uses less memory because it reads one line at a time.
```python
with open(filename, 'r') as inputfile:
    for line in inputfile:
        # Lines have a '\n' at the end, like inputfile.readlines().
        print(line, end='')
```

#### Accessing attributes which start with underscores
“Private” instance variables that cannot be accessed except from inside an object don’t exist in Python.  Since there is a valid use-case for class-private members (namely to avoid name clashes of names with names defined by subclasses), there is limited support for such a mechanism, called name mangling. Any identifier of the form __spam (at least two leading underscores, at most one trailing underscore) is textually replaced with _classname__spam, where classname is the current class name with leading underscore(s) stripped.

So to access attributes which start with underscores simply run obj_name._ClassName__attr_name .
```python
class MyClass:

    def __init__(self):
        self.__private_attr = None

    def set_private_attr(self, attr_to_private):
        self.__private_attr = attr_to_private


attr = 7

my_class = MyClass()
my_class.set_private_attr(attr)

print(my_class._MyClass__private_attr)
```