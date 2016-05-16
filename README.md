## Python tips

List of python tips

1. [Reverse a string or list](#reverse-a-string-or-list)
1. [Reverse by custom step](#reverse-by-custom-step)
1. [List slice assignment](#list-slice-assignment)
1. [Check file or directory exists](#check-file-or-directory-exists)
1. [Call an external command](#call-an-external-command)
1. [Ternary conditional operator](#ternary-conditional-operator)



#### Reverse a string or list
```python
list = ['a','b','c','d','e']
reverse_list = list[::-1]

string = "python"
print string[::-1]
```

#### Reverse by custom step
```python
list = ['a','b','c','d','e']
reverse_list = list[::-2]
```

#### List slice assignment
```python
  list = ['a','b','c','d','e']
  list[3:] = ['x','y','z']
  print list
  #output : ['a', 'b', 'c', 'x', 'y', 'z']
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


