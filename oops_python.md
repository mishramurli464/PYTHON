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
2)**priate member**-- accesible within class. accessible via methods only.  
3)**protected member**-- This convention indicates that they are intended for internal use within the class and its subclasses. However, they can still be accessed from outside the class.   

class Finance:

def _init_(self):

self.revenue=100000

self.number_of_sales=114

f1=Finance()

print(f1.dict)

class HR:

def _init_(self):

self.number_of_emp=32

f1.revenue=1

h1=HR()

print(f1.dict)
