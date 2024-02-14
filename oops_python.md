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
``py
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
