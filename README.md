## Python tips

List of python tips

1. [Reverse a string or list](#reverse-a-string-or-list)
1. [Reverse by custom step](#reverse-by-custom-step)
1. [List slice assignment](#list-slice-assignment)
1. [Copy a list](#copy-a-list)
1. [Create a list out of string](#create-a-list-out-of-string)
1. [Check file or directory exists](#check-file-or-directory-exists)
1. [Call an external command](#call-an-external-command)
1. [Ternary conditional operator](#ternary-conditional-operator)
1. [for else](#for-else)



#### Reverse a string or list
```python
my_list = ['a','b','c','d','e']
reverse_list = my_list[::-1]

my_string = "python"
print my_string[::-1]
```

#### Reverse by custom step
```python
my_list = [1,2,3,4,5,6]
reverse_list = my_list[::-2]
# output : [6,4,2]
```


#### List slice assignment
```python
  my_list = ['a','b','c','d','e']
  my_list[3:] = ['x','y','z']
  print my_list
  #output : ['a', 'b', 'c', 'x', 'y', 'z']
```


#### Copy a List
```python
a = [1, 2, 3, 4]
''' Considered as one of the weirdest syntax to copy elements.'''
a_copy = a[:]
```


#### Create a list out of string
```python
data = "abcd"
data_list2 = list(data)  # OutPut: data_list = ['a', 'b', 'c', 'd'] 
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

#### Call an external command
```python
from subprocess import call
call(['ls,'-l'])
```

#### Ternary conditional operator
```python
print 'True' if True else 'False'
```


#### for else
```python
 my_string = ""
    for i in my_string:
        print i
    else :
        print 'String is empty'
```
