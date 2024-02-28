# Built-in class function  
*getattr(object_name, attribute_name)*-->retriving the attribute value for the specified object  
*setattr(object_name, attribute_name, new_value)*--> for updating new value to the attribute for the specified object  
*delattr(object_name, attribute_name)*--> removing the the attribute for the specified object  
*hasattr(object_name, attribute_name)*--> for checking if the attribute is present for the specified object  
**ex**  
```py
class Employee:
 def __init__(self,name,id):
  self.id=id
  self.name=name

 def show_details(self):
  print(f"the name of employee bearing id {self.id} is {self.name}")
e1=Employee("mur",2)
e1.show_details()
print(getattr(e1, "id"))
setattr(e1, "id",5)
print(e1.id)
print(e1.__dict__)
delattr(e1, "id")
print(e1.__dict__)
hasattr(e1, "id")
```  
# Built-in class atribute
____dict____ :- Dictionary containing class's namespace  
__doc__ - Class documentation string.  
__name__ :- Class Name  
__module__ :- Module name in which class is defined  
__bases__ :- List of base classes  
**ex**
```py
class Employee:
'''This is employee class for maintaining employee data'''
def __init__(self, nm, ag):
 self.name=nm
 self.age=ag
def display(self):
 print(f"name is: {self.name} and age is {self.age}")
 
e1=Employee('jay',21)
e2-Employee('raj',22)

print(Employee._doc_)
print(Employee.__dict__)
print(Employee.__name__)
print(Employee.__module__)
```
# INHERITANCE  
'''Inheritance is a fundamental concept of object-oriented programming (OOP) that allows a class to inherit properties and methods from another class'''    
**ex 1**
-->The __init__() function is called automatically every time the class is being used to create a new object.it is also called as constructor.  
```py
class Employee:
 def __init__(self,name,id):
  self.id=id
  self.name=name

 def show_details(self):
  print(f"the name of employee bearing id {self.id} is {self.name}")

class Programmer(Employee):
 def showlanguage(self):
  print("the default language is python")

e1= Programmer("murli",420) #multiple objects can be created for each class
e1.show_details()
e1.showlanguage()
```

**ex 2**  
--> the super() function is used to refer to the parent class or superclass.It allows you to call methods defined in the superclass from the subclass,  
enabling you to extend and customize the functionality inherited from the parent class.  
```py
class Employee:
 def __init__(self,name,id):
  self.id=id
  self.name=name

 def show_details(self):
  print(f"the name of employee bearing id {self.id} is {self.name}")

class Programmer(Employee):
 def showlanguage(self,name,id,lang):
  super().__init__(name,id)
  self.lang=lang
  print("the default language is: ",lang)

e1= Programmer("murli",420)
e1.show_details()
e1.showlanguage("murli",420,"python")
```
## types of inheritance 
**Single Inheritance**: In single inheritance, a class inherits from only one base class. This is the simplest form of inheritance.  
```py
class BaseClass:  
    pass

class DerivedClass(BaseClass):  
    pass  
```

**Multiple Inheritance**: Multiple inheritance allows a class to inherit attributes and methods from more than one base class.  
```py
class BaseClass1:  
    pass  

class BaseClass2:  
    pass  

class DerivedClass(BaseClass1, BaseClass2):
    pass
```

**Multilevel Inheritance**: In multilevel inheritance, a class is derived from a class which itself is derived from another class.   

```py  
class BaseClass:
    pass

class DerivedClass1(BaseClass):
    pass

class DerivedClass2(DerivedClass1):
    pass  
```

**Hierarchical Inheritance**: Hierarchical inheritance involves multiple derived classes inheriting from the same base class.

```py  
class BaseClass:
    pass

class DerivedClass1(BaseClass):
    pass

class DerivedClass2(BaseClass):
    pass
```  
**Hybrid Inheritance**: Hybrid inheritance is a combination of more than one type of inheritance. It's a mix of single, multiple, multilevel, or hierarchical inheritance.  
```py  
class BaseClass1:
    pass

class BaseClass2:
    pass

class DerivedClass1(BaseClass1):
    pass

class DerivedClass2(BaseClass1, BaseClass2):
    pass
``` 
# Encapsulation 
Wrapping up data and methods working on data together in a single unit(i.e class) is called encapsulation.  
![image](https://github.com/mishramurli464/PYTHON/assets/128781536/e64a7c53-4ccf-44b6-8c23-4ea58c638d83)  

**Data hiding** in encapsulation refers to the practice of restricting access to certain attributes or methods of a class, typically to prevent direct modification or manipulation   
from outside the class.   
**Access modifiers** it is basically used to resolve data hiding.(it basically restrics data access outside the class in encapsulation)  
it can be achieved  by declaring the data members and methods of class as priate.  
types--  
1) **public member**-- accessible anyhwere outside the class by using object refrence.
   ```py
   class MyClass:
    def __init__(self, x):
        self.x = x  # public attribute

    def display(self):
        print(self.x)  # public method

   obj = MyClass(5)
   print(obj.x)  # accessing public attribute
   obj.display()  # calling public method
   ```
2)**priate member**-- accesible within class. accessible via methods only.   
```py
class MyClass:
    def __init__(self, x):
        self.__x = x  # private attribute

    def __display(self):
        print(self.__x)  # private method

obj = MyClass(5)
# print(obj.__x)  # This will raise an error
# obj.__display()  # This will raise an error
```
3)**protected member**-- This convention indicates that they are intended for internal use within the class and its subclasses. However, they can still be accessed from outside the class.  
## Name mangling  
it is a concept used in python to access private data outside the class.  
```py
class MyClass:
    def __init__(self):
        self.__private_attribute = 42

    def __private_method(self):
        return self.__private_attribute

obj = MyClass()

# Accessing private attribute and method using name mangling
print(obj._MyClass__private_attribute)  # Outputs: 42
print(obj._MyClass__private_method())   # Outputs: 42
```
## Advantages of encapsulation  
 1) Security
 2) simplicity
 3) prevents accidental modifications  

# Polymorphism  
real life ex- me infront of my parents and me in front of my friends  
Polymorphism in Python refers to the ability of python object to take many forms.  
if a variable, object or a method performs different beavior according to situation is called polymorphism.  
ex- '+' , 'len()' etc can perform different behavior at diferent situations.  
## polymorphism in inheritance
ex-  
```py
class Veh:
  def __init__(self,name, color,price):

   self.name=name

   self.color=color

   self.price=price

  def get_details(self): 
   print("name is:", self.name) 
   print("color is:", self.color)
   print("price is:", self.price)

  def max_speed(self):
   print("maximum speed limit is 100")

  def gear(self):
   print("gear change is 6")

class Car(Veh):

  def max_speed(self):
   print("maximum speed limit is 140")

  def gear(self):
   print("gear change is 6") 

v1=Veh("bike",'black',10000)
c1=Car("ferrari","red",10000000)
v1.max_speed()
c1.max_speed()
```  
--in the above ex we can see same method (i.e max_speed()) for different objects giving different values.

## over riding built-in function

Overriding built-in functions in Python involves defining a method in a class with the same name as a built-in function, thus changing its behavior for instances of that class. This is a form of polymorphism where the behavior of a built-in function is altered for objects of a specific class.  
 ex-
```py
class cart:
  def __str__(self):
   return "its a cart class"
c1=cart()
print(c1)
```
output-- **its a cart class**  

ex1--  
```py
class Cart:
 def __init__(self, basket1, basket2,basket3):

  self.clothes=basket1

  self.electronics=basket2

  self.other=basket3

 def __len__(self):

  print("total numbe rof items in cart:")

  return len(self.clothes)+len(self.electronics)+len(self.other)

shantanu=Cart(['pant', 'shirt', 't-shirt'], ['earphone', 'mobile'], ['chair'])

print(len(shantanu)) #6
```
-- in the above ex the __len__ function is over riden in the class for its instance.  
## operator overloading  
When same operator behaves differently depending on values.  
You can assign a new meaning to operators also and you can extend functionality of operators  
You can change default behaviour of operator using over-riding.  
```py
num1=10
num2=20
num3="10"
num4="20"
print(num1+num2) #30
print(num1.__add__(num2)) #30
print(int.__add__(num1, num2)) #30
print(num3+num4) #1020
print(num3.__add__(num4)) #1020
print(str.__add__(num3, num4)) #1020
print(dir(int))

#step-1:- check datatype of left operand. #int
#step2:- go in that class
#step3:- call_add_() function
```
--in the above example operator(i.e"+") behaving differently for different values  

**ex-2** 
```py
#overload > operator
class Hotel:
 def __init__(self,name, fare):
  self.name=name
  self.fare=fare
  
 def __gt__(self,other): #(h1,h2)
  return self.fare>other.fare

#h1.fare>h2.fare

h1=Hotel('Taj hotel', 20000)
h2=Hotel('Panchratna', 10000)
print(h1>h2) #True
```
## Method overloading
when a class contains two or more methods with samne name but different behavior is called method overloading. 
However, unlike some other programming languages such as Java or C++, Python does not support traditional method overloading based on the number or type of arguments. Instead, Python utilizes a technique called "polymorphism" or "duck typing" to achieve similar functionality.  
```py
class Addition:
 def add(self,num1,num2):
   print("addition is:", num1+num2)

 def add(self,num1, num2,num3): 
   print("addition is:",num1+num2+num3)

a=Addition()
#a.add(10,20)
a.add(10,20,30)
```
-- in the above example as python doesnot support polymorphism so here the last method in the class(i.e def add(self,num1, num2,num3)) will be called  and hence it will give type error for "a.add(10,20)"
## how to achieve method overloading  

In Python, method overloading can be achieved through a combination of default arguments and variable-length argument lists. By defining a single method with default arguments or by using *args( a waay to take arguments as a tupple) and **kwargs( a waay to take arguments as a dictonary), you can create a flexible method that can handle different combinations of arguments.  
ex-1->  **Using default arguments**  
```py
class Calci:

  def add(self, num1=None, num2=None, num3=None):

   if num1!=None and num2!=None and num3!=None:
     print("Addition is:", num1+num2+num3)

   elif num1!=None and num2!=None: 
    print("Addition is:", num1+num2)

   else:
    print("incorrect parameters provided")

c1=Calci()

c1.add(10,20)

c1.add(10,20,30)
```
```py
class Area:

 def area(self,l=0,b=0):

  if l>0 and b>0:
   print("area of rectangle:",l*b)

  elif l>0 and b==0:
   print("area of sqaure is:",l*l)

a=Area()

a.area(10) #100

a.area(10,20) #200
```

ex-2--> **Using Variable-length Argument Lists (*args):**  
```py
class MyClass:
    def my_method(self, *args): # "*args" it is a waay to take arguments as a tupple
        if len(args) == 0:
            print("No arguments")
        elif len(args) == 1:
            print("One argument:", args[0])
        else:
            print("Multiple arguments:", args)

obj = MyClass()
obj.my_method()          # No arguments
obj.my_method(10)        # One argument: 10
obj.my_method(10, 20)    # Multiple arguments: (10, 20)
```

# Nested Class   
In Python, you can define a class inside another class, which is known as nested classes.   
Nested classes are useful when you have a class that is closely related to another class and doesn't make sense to be used outside of it.  
It helps in keeping the code organized and expressing the relationship between the classes.  
ex-1->  
```py
class Car:
    def __init__(self, make, model):
        self.make = make
        self.model = model
        self.engine = self.Engine(1500)  # Creating an instance of the nested Engine class

    def drive(self):
        print(f"Driving {self.make} {self.model}")

    class Engine:
        def __init__(self, horsepower):
            self.horsepower = horsepower

        def start(self):
            print("Engine started")

        def stop(self):
            print("Engine stopped")

# Creating an instance of the Car class
my_car = Car("Toyota", "Camry")

# Accessing attributes and methods of the Car class
print(f"Car: {my_car.make} {my_car.model}")
my_car.drive()

# Accessing attributes and methods of the nested Engine class through the instance of the Car class
print(f"Engine horsepower: {my_car.engine.horsepower}")
my_car.engine.start()
my_car.engine.stop()
```
--We define a Car class that has an attribute make, model, and a nested class Engine.  
  The nested Engine class represents the car's engine, containing an attribute horsepower.  
  The Car class creates an instance of the Engine class (engine) in its constructor.
  We create an instance of the Car class (my_car) and access its attributes and methods, as well as those of the nested Engine class.   
  
## Accessing Members of One Class Inside Another Class   
--In Python, you can access members (attributes and methods) of one class inside another class by creating an instance of the first class within the second class or by passing an instance of the first class as an argument to the methods of the second class. This allows you to use the attributes and methods of the first class as if they were part of the second class.  
```py
class Dog:
    def __init__(self, name):
        self.name = name

    def bark(self):
        print(f"{self.name} says Woof!")

class Person:
    def __init__(self, dog_name):
        self.dog = Dog(dog_name)  # Creating an instance of the Dog class

    def greet_dog(self):
        print(f"Hello {self.dog.name}!")
        self.dog.bark()  # Accessing the Dog's bark method

# Creating an instance of the Person class
person = Person("Buddy")

# Accessing methods and attributes of the Dog class through the instance of the Person class
person.greet_dog()
```
---We define two classes, Dog and Person.
The Dog class has an attribute name and a method bark() to simulate a dog's bark.   
The Person class has an attribute dog which is an instance of the Dog class.  
The Person class also has a method greet_dog() which greets the dog and triggers the dog's bark() method.  
When we create an instance of the Person class and call the greet_dog() method, it accesses the name attribute and bark() method of the Dog class through the dog attribute of the Person instance.  

# Destructor  
A special method(__del__()) which destroys object and releases resources tied to the object.  
the tied resource is basically the database connection, cache created etc.   
Destructor is called automatically when the object is destoyed.  
**garbage collecter**  
a program to delete refrences.  
it runs automatically.  
it does memory management.  

destructor ex--  
```py
class vsp:
 def __init__(self): 
  print("Hi This is Constructor Method")

 def my(self): 
  print("this is Normal Method ")

 def __del__(self):
  print("Destructor Method Called..") 
  print("Object Deleted......")

ob=vsp ()
ob.my ()
del ob
```

## Storing objects in List  
```py
class Movie(object):

 def __init__(self, title,mins, hero):
  self.title=title
  self.runtime=mins 
  self.hero=hero

 def printer(self):
  print(f"Title is : {self.title}\nruntime is: {self.runtime}\nhero is: {self.hero}")

list_of_movies=[]

while True:

  title=input("Enter the title of movie:")

  mins=input("Enter the runtime of movie:")

  hero=input("Enter the name of hero of movie:")

  obj=Movie(title,mins, hero)

  list_of_movies.append(obj)

  print("Movie added into the list")

  ans=input("Do you want to add another movie(y/n)")

  if ans!='y':
   break
        
print("All movies information:")
for obj in list_of_movies:
        obj.printer()
```  

# Decorators in python   
Decorators in Python are functions that modify or enhance the behavior of other functions or methods. They allow you to wrap additional functionality around existing   
functions without modifying their code directly.   

**1) Function decorators**   
-- 
```py
def div(a,b):
  print(a/b)

def smart_div(func): # function decorator
  def inner (a,b):
   if a<b:
    a,b = b,a
   return func(a,b)
  return inner

div1=smart_div(div)
div1(2,4)
```
**2) Class decorators** 
Class decorators are decorators that are applied to classes instead of functions. They can be used to modify the behavior of a class, such as adding new methods or attributes,   
without modifying the class itself. Class decorators are defined similarly to function decorators but take a class as input instead of a function. Here's a basic example:  
```py
def my_class_decorator(cls):
    class NewClass(cls):
        def new_method(self):
            print("New method added to the class")
    return NewClass

@my_class_decorator
class MyClass:
    def existing_method(self):
        print("Existing method of the class")

obj = MyClass()
obj.existing_method()
obj.new_method()
```

**2) Decorator Classes**   
Decorator classes are a variation of decorators where the decorator itself is implemented as a class instead of a function. Decorator classes implement the "__call__()" method to define their behavior, and instances of the decorator class can be used to wrap around functions or methods. Here's an example:  
```py
class MyDecorator:
    def __init__(self, func):
        self.func = func

    def __call__(self, *args, **kwargs):
        print("Something is happening before the function is called.")
        result = self.func(*args, **kwargs)
        print("Something is happening after the function is called.")
        return result

@MyDecorator
def my_function():
    print("The original function is called.")

my_function()
```
# Abstraction  
The process by which data and functions are defined in such a way that only essential details can be seen and unnecessary implementations are hidden is called Data Abstraction.   
Hiding complex implementation details and showing only signatures to users.  

## How abstraction achieved in python :-

--By using abc module :- ABC class  
                         abstractmethod  
--Inherit your class from ABC class  
--Create abstract methods in your abstract class.  

**Syntax:-**
```py
from abc import ABC,abstractmethod   
class Employee(ABC):
  #abstract methods 
  #concrete methods     
#Abstract methods:- method that has a declaration but does not have an implementation.    
#Concrete methods:- Normal methods    
```
ex--  
```py
from abc import ABC, abstractmethod

class Car(): 
  @abstractmethod
  def mileage(self):
    pass
  
  def color(self): 
    print("white")

class Maruti_Suzuki(Car):
  def mileage(self): 
    print("mileage is 30kmph")

class TATA(Car):
  def mileage(self): 
    print("mileage is 35 kmph")

class Duster(Car):
  def mileage(self): 
    print("mileage is 40kmph")

m1=Maruti_Suzuki()
t1=TATA()
d1=Duster()
t1.mileage() 
```

**Abstract class :-**  
-A class which contains one or more abstract methods and concrete methods.  
-Abstract class must have at least one abstract method.   
-An abstract class can be considered as a blueprint for other classes.  
-A class which is inherited from ABC class.   

**Keep in mind..**  
-You can't instantiate abstract classes.  
-Abstract class requires at least one method abstract.  
-All abstract methods present in abstract class must be implemented in child classes. Else, child class becomes abstract.  
-If there is abstract method in class, that class must be abstract class.  

**Uses of abstraction:-**  

1. when we have large code and functionalities.  
2. Your abstract class is like an API for other subclasses.  
3. used when a third party is going to provide implementations.  
4. When we have different implementations for different objects for same component.  
5. For creating interfaces.  
