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
'''py
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



