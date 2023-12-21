# INHERITANCE  
'''Inheritance is a fundamental concept of object-oriented programming (OOP) that allows a class to inherit properties and methods from another class'''   
-->The __init__() function is called automatically every time the class is being used to create a new object.it is also called as constructor.  
**ex 1**
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

e1= Programmer("murli",420) //multiple objects can be created for each class
e1.show_details()
e1.showlanguage()
```
--> the super() function is used to refer to the parent class or superclass. It allows you to call methods defined in the superclass from the subclass,  
enabling you to extend and customize the functionality inherited from the parent class.   
