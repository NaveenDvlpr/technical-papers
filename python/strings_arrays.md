# Python Strings & Arrays

## Strings
Strings in Python are immutable. It means we can't change a character in the string directly. Sring is a class in Python.
* A single characted is treates as a string of length one.
* Srings are comonly used for text handling and manipulation.
* Provides index based accessing. Negative index represents position from right.

##### String creation
```py
message = "Hello world!"
message2 = 'Hello world!!'
message3 = """ Hey! it has been long time seeing you.
Would like to meet you?
"""
```

##### String slicing
```py
city = "Solapur"
print(city[1:4]) # ola
print(city[1:]) # olapur
print(city[:4]) # Sol
print(city[::-1]) # rupaloS
```
##### Important string methods
```py
string1.replace("pattern1", "pattern2")
length = len(string1)
print(message.lower())
print(message.upper())
string.strip() # removes any spaces or mentioned characters around the string.
name = "Hari"
print(name*3) # HariHariHari
print(f"Hey! {name}, where are you?")
print("ri" in name) # True
```

## Arrays
Python doesnot have in-built way to working with arrays. However, it offers various ways to work linear data structures. We import array library from the standard library to work with arrays.

Array is a collection of elments stored at a contiguous memory locations, used to hold multiple values of the same data type. Arrays rquires a typicode initialization to define the data tupe.

```py
import array as arr
a = arr.array('i', [1,2,3])
a.append(6)
print(a)
```
A typicode mentions the datatupe and size of each element in the memory

| Typecode | Type | Bytes |  
| 'b' | int | 1 |  
| 'i' | int | 4 |
| 'f' | float | 4 |
| 'd" | double | 8 |

##### Importand array functions
```py
a = arr.array('i', [2,3,4])
print(*a) # spreads array
a.insert(1, 4) # index, value
a.remove(1) # removes the firt occurence of the value
a.pop(2) # removes the element at index 2
```

Slicing and searching is same as strings.
Methods are similar as list methods.
