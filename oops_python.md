#INHERITANCE
'''Inheritance is a fundamental concept of object-oriented programming (OOP) that   
allows a class to inherit properties and methods from another class'''  
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

e1= Programmer("murli",420)
e1.show_details()
e1.showlanguage()
```
