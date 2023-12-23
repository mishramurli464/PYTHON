# Built-in class function  
*getattr(object_name, attribute_name)*-->retriving the attribute value for the specified object
*setattr(object_name, attribute_name, new_value)*--> for updating new value to the attribute for the specified object
*delattr(object_name, attribute_name)*--> removing the the attribute for the specified object
*hasattr(object_name, attribute_name)*--> for checking if the attribute is present for the specified object


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

