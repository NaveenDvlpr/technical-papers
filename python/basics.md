# Python Basics

Python is a high-level interpreter language. 

### Variables
Python follows dynamic typing on variables.
```python
a = 10
type(a) # Integer type
a = "Syam"
type(a) # String type
```

Swaping valriable
```python
a = 10
b = 20
a,b = b,a
```

### Datatypes
* Text Type:	str
* Numeric Types:	int, float, complex
* Sequence Types:	list, tuple, range
* Mapping Type:	dict
* Set Types:	set, frozenset
* Boolean Type:	bool
* Binary Types:	bytes
* None Type:	NoneType

### Operators
Operator are used to perform a specific operation in python.

##### Arithmetic operators
* a + b --> add two numbers
* a - b --> subtract b from a
* a * b --> multiply two numbers
* a / b --> float division
* a // b --> integer division
* a % b --> remainder of a divided by b

##### Relational operators
* a == b --> a is equal to b
* a != b --> a is not equal to b
* a <= b --> a is less than equal to b
* a >= b --> a is greater than equal to b

##### Logical operators
* and --> both conditions must have to be true
* or --> either of the conditons must have to be true
* not --> condition must not be true


### Loops
Loops are control statements. They are used to iterate a block of code for mentioned iterations.

##### while
```py
    start, end = 1, 5
    while start <= end:
        print(start)
        start += 1
    # 1, 2, 3, 4, 5
```
Best choice for game loops and we don't know the exact iterations before.

##### for
```py
    for i in range(10)
    print(i)

    numbers = [i for i in range(19)]
```
Best choice when we know the starting value of the loop variable and number of iterations.


### Tuple()
A tuple is an immutable, ordered, and heterogenous collection of elements. Tuples allow indexed based searching and slicing. Negative indexing is accepted as well.

##### Important tuple examples.
```python
    tup = () # Empty tuple
    tup = ([1,2,3,4]) # converting list to tuple
    tup = tuple("MountBlue")
    tup1 = (1,2)
    tup2 = (2,3)
    tup3 = tup1+tup2
    print(tup[::-1])
    del tup
    a, *b, c = (1,2,3,4) # b = [2, 3]
```

##### Two tuple methods
count(element)
```py
    tup = (1,3,4,1,3)
    print(tup.count(3)) # 2
```
index(element, after_index)
```py
    tup = (1,3,4,1,3)
    print(tup.index(3, 3)) # 4
```

### List[]
A list is an mutable, ordered, and heterogenous collection of elements. Lists allow indexed based searching and slicing. Negative indexing is accepted as well.

Python list stores references to objects, not the actual values directly. Reassigning an immutable object creates a new object instead of changing the old one.

##### Important list examples
```py
    a = [1, 2, ["abc", [34.5, "abc"]]]
    b = ["ABCD"] # b = ['A', 'B', 'C', 'D']
```

##### List methods
```py
list.append(element)
list.extend(iterable)
list.insert(index, x)
list.remove(x)
list.pop(index)
list.clear()
list.index(x)
list.count(x)
list.sort(reverse=True)
list.reverse()
list.copy()
```

### Dictionary
A mutable built-in data structure that stores data in key-value pairs, mapping, unique keys to specific values. Implemented as a hashmap, it allows faster data retrieval.

We can created nested dictionaries as well.

##### Important examples
```py
data = {
    "name": "Naveen",
    "age": 35,
    "location": "Abholadbavi nagar"
}

b = dict(name="Aruna", age = 25)

print(data["name"])
del data["location"]
```

##### Important methods
pop(key) --> removes the item with the given key values
popitem() --> removes and returns the last inserted key-value pair in the last.
clear() --> clears the dictionary
get() --> Returns the value associated with a specified key return None if key not found.
update(new_dict) --> updats the existing keys in the old dictionary and inclueds the new keys in the new dictionary.
setdefault(key, value) --> Returns the value of the key if exists. If not sets the key-value pair in the dictionary.
dict.fromkeys(keys, default_value)

##### Iteration
```python
d = {"a": 1, "b": 2}
for key, value in d:
    print(key)
    print(value)

for key in d:
    print(key)

for value in d.values():
    print(value)
```
