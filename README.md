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
1. [else in for loop](#else-in-for-loop)
1. [Print to file](#print-to-file)


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

''' Another way of copying a list.'''
a_copy2 = list()
a_copy2.extend(a) # output a_copy2 = [1, 2, 3, 4]
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


#### `else` in `for` loop
An `else` block is executed if the loop body is not terminated by a `break` statement : 

```python
for i in range(5):
    print('Here we go!')
    if i == 2:
        break
else:
    print('There we went.')
else :
    print 'String is empty'
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
output = open('file.txt','w')
print >>output, "Python!!"
```
