# Object Oriented Programming and SOLID Principles

## Object Oriented Programming
Object oriented programming is a programming paradigm. We group the data and behaviour of data into user-defined data types called classes. This way of programming allows us organization and cleanliness. Code resability and easier collaboration. Video games are best to model through object oriented programming.

##### Class
A class is a user defined datatype. It is a blueprint of object. In class we declare the properities and behavious of the objects of the class. Class is never instantiated. 

##### Object
An object is an instance of the class. Which means using the class as a blue print we create an object in the memory which has its own variables(properties) and functions(behaviours) to work with.

```python
class Student:
    def __init__(self, name, age, gender):
        self.name = name
        self.age = age
        self.gender = gender

student1 = Student("Kiran", 42, "F")
```
### Objected Oriented Programming Principles
##### Encapsulation
The process of binding the properties(instance variables) and behaviours(methods) of an object into a single unit in the memory as an object is called encapsule. Objects have capsule like modelling of data and fuctions. It makes the variables of an object unaccessible outside environment.
```py
class Person:
    def __init__(self, name, age):
        self.name = name
        self.__age = age # __age is a private variable. Cannot be accessed directly.

    def get_age(self):
        return self.__age

    def set_age(self, age):
        if age <= 0:
            print("Age must be a positive.")
        else:
            self.__age = age
```
Benefits:
* Data Protection
* Validation
* Flexibility
* Control

##### Inheritance
Extensiong of class to child classes. Offers code reusability
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def make_sound(self):
        print("Making sound...")

class Dog:
    def __init__(self, name):
        super().__init__(name)
        self.sound = "Barking..."

    def make_sound(self):
        print(self.sound)
```
**super()** function is used to call methods of the super class. It follows Method Resolution order.

Benefis:
* Code reusability
* Real-world mapping
* Easy maintainence
* Provides polymorphism

### Polymorphism
Changing the behaviour of a function during runtime is called polymorphism. This make sures the calling function does not depend the implementation of called functions. Muliple behaviour of a function is called polymorphism.
* **Compile-time polymorphism**
* **Run-time polymorphism**

Python uses *args, *kwargs to provided method overloading which is a compile-time polymorphism.

Runtime polymorphism means that the behaviour of a method is decided while program is running, bases on the object calling it. This happens through Method Overriding a child class.
```python
class Animal:
    def __init__(self, name):
        self.name = name

    def make_sound(self):
        print("Making sound...")

class Dog:
    def __init__(self, name):
        super().__init__(name)
        self.sound = "Barking..."

    def make_sound(self):
        print(self.sound)

dog = Dog("Snoppy")
dog.make_sound()
```

### Abstraction
Hiding the complex background implementation details and only showing the essential features to the user.
##### Abstract Base Class
Abstract classes are used to acheive data abstraction by defining a common interface for its subclasses. They cannot be instantiated directly.

```py
from abc import ABC, abstractmethod

class Greet(ABC):
    @abstractmethod
    def say_hello(self):
        pass

class English:
    def say_hello(self):
        return "Hello!!"
        
s = English()
print(s.say_hello())
```

## SOLID Principles

These are the standard principles which we should follow while writing the code to support better readibility, extensibility and decoupled code.

**S** - Single responsibility principle  
**O** - Open and Close principle  
**L** - Liskov substitution principle  
**I** - Interface segregation principle  
**D** - Dependencies inversion principle 

##### Single Responsibility Principle
A class should have one and only one reason to change.

We should not make a function or class to be changed for multiple reasons. They should solely responsible for one objective. It does not mean we have to create an individual class for each method. Cohesive methods should be under same class.

```py
class Order:
    def __init__(self, customer_id, customer_name, items):
        self.customer_id = customer_id
        self.customer_name = customer_name
        self.items = items

    def getPrice(self):
        total = 0
        for item in items.values():
            total += (item["price"]*item["quantity"])
            return total

    def take_payment(payment_type, total):
        print(f"Processed payment using {payment_type}")

    def send_notification(notification_service):
        print(f"Sent a notitication to {self.customer_name} using {notification_service}")
    
    def checkout(self, payment_type, notitication_type):
        total = self.getPrice()
        take_payment(payment_type, total)
        send_notification(notification_service)
        print("Checkout successful....")
```

In the above example we can observe that the Order class is doing so many responsibilites
* Taking order
* Calculationg total
* Processing payment
* Sending notification

The class needs to be updated when there is a discount change on the total, we follow different procedures for different payment type and sending a notification is completely different responsibitly than placing order. An order class should take an order and complete checkout

```py
class Order:
    def __init__(self,
        customer_name, items, payment_type,
        notificaiton_service, inventory_manager, payment_manager, notification_manager):
        self.customer_name = customer_name
        self.items = items
        self.payment_type = payment_type
        self.notificaiton_service = notificaiton_service
        self.inventory_manager = inventory_manager
        self.payment_manager = payment_manager
        self.notification_manager  = notification_manager

            
    def checkout():
        total = self.inventory_manager.get_total(self.items)
        payment_status = self.payment_manager.process_payment(self.payemt_type)
        if payment_status:
            self.notification_manager.send_notification(notification_service)
            print("Order has been placed successfully..")
        else:
            print("Sorry, payment error. Try with a different payment method.")
A
class inventoryManagement:
    def __init__(self):
        pass
    def get_total(self, items):
        pass

class NotificationService:
    def __init__(self):
        pass
    def send_notification(self, notificaiton_service):
        pass
    
class PaymentService:
    def __init__(self):
        pass

    def process_payment(self, payment_type):
        pass

```
