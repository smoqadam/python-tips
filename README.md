## Python tips

List of python tips

1. [Reverse a string or list](#reverse-a-string-or-list)
1. [Reverse by custom step](#reverse-by-custom-step)
1. [List slice assignment](#list-slice-assignment)



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


  
