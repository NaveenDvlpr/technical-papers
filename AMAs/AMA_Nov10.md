# AMA - CLI, GIT and Python
##### Date : Nov 10 2026

### Why do we need abstraction?
Abstraction is hiding unnecessary implementation details and showing the relevant thins to the end user. In OOP, abstraction can be achieved using abstract classes and interfaces/abstract methods.
### what does lstrip() do?
lstrip() method is used to remove the leading whitespace or other irrelevant characters from the left side.
```python
message = " ** Hello world!"
print(message.lstrip("* "))
print(message)

# Output:
# Hello world!
#  ** Hello world!
```

### Diff erence between remove() and pop() in python?
* remove(\<value>) function is used to delete a specific value. Returns None on success and ValueError if value is missing.
* pop(\<index>) function is used to delete the element at a specified index. Returns the deleted value on success and IndexError if index is out of range.
### What is multilevel inheritance?
When a sub class inherits from a super class which is a sub class of a super class is called multi-level inheritance.  

Super class --> Intermediate class --> Sub class  
Here --> refers to "extends"
              
### Use of exception handling
While a program is running we may encounter unexpected runtime errors. This may result the termination of the program. To prevent unwanted terminations we handle the possible errors using exception Handling.
```python
a = 10
b = 0
try:
  res = a/b
  print(res)
except ZeroDivisionError:
  print("Division by zero is not possible..")
finally: # This runs no matter what
  print("Program finished..") 
```
### How does CLI works?
**CLI** (Command-Line Interface) is a text-based interface through which users interact with a computer by entering commands. A shell such as Bash interprets those commands and executes the corresponding programs or operations.

### Use of README.md
README.md in a project is used to explain about the project. 
* What the project does?
* Why we implemented the project?
* Technologies used
* How to run the project?
* Sources and credits for the contributors
* Any other relevant informatiion
### Do we need to import to implement abstract
Yes, we need to import an in-built module to create an abstract class
```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass
```
### What is hierarchical inheritance
Multiple child classes derived from a single parent class is called hierarchical inheritance.  
Parent class --> Child classA  
Parent class --> Child classB
### What is single inheritance
When a single child class is derived from a single parent class is called Single inheritance.

Parent class --> Child Class

### Use of .gitignore file
**.gitignore** file is used to ignore the folders and files we don't want others to see in our remote repository. It includes the enviroment variables and other test configurations which we don't want to expose. 

.gitignore tells Git which untracked files/directories it should not normally track.

### Difference between "init" and "new"
* \_\_init__ is used to initialize an object. It is used to setup the instance variables of the class. It accepts object reference(self) as its first arguement.
* \_\_new__ is used to allocate memory and create a raw object. It accepts class(cls) as its first argument. Using \_\_new__ provides a flexible way to create an object. It is the real constructor.
### How to create a typed array
To create a typed array we use array method with a typecode. 'i' for integer(4 bytes) array.
```python
import array as arr

new_array = arr.array('i', [1,2,3])
print(new_array)

#ouput:
# array('i', [1, 2, 3])
```
### how does string slicing works
Slicing means getting a desired substring from the string. This sample codes shows few ways.
```python
web_series = "Money Heist"
print(web_series[3:])
print(web_series[:5])
print(web_series[2:7])
print(web_series[::-1])

# Outputs:
# ey Heist
# Money
# ney H
# tsieH yenoM
```

### What is "\_\_str__"?
When we print an object directly. It prints the class name of the object and it's memory reference. Using \_\_str__ we can override this functionality. Creating our own print for the objects.

### When we use for and while
* When we know the starting value of the loop variable and number of iterations needed. It is better to use for loop.
* When we don't know the exact number of iterations. We want the application loop run as per the user preferences. It is better to use the while loop.

### Explain git rebase
Using git rebase reapplies a sequence commits from one branch onto a new base branch. This removes the cluttered look of commits and gives us a linear representation of the commits happened. Providing a cleaner commits lookup.
```bash
git rebase <targe-branch>
```
