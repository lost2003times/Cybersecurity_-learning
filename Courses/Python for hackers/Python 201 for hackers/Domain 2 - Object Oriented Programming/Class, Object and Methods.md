___
## Input 
```
class Person:

    'Person base class'

    wants_to_hack = True

    def __init__(self,name,age):

        self.name = name

        self.age = age

  

    def print_name(self):

        print("My name is {}".format(self.name))

  

    def print_age(self):

        print("My age is {}".format(self.age))

  

    def birthday(self):

        self.age += 1

  
  

bob = Person("bob", 25)

alice = Person("Alice", 32)

sherry = Person("Sherry", 23)

  

print(bob)

print(alice)

print(sherry)

  

bob.print_name()

alice.print_name()

sherry.print_name()

  

bob.print_age()

alice.print_age()

sherry.print_age()

  

bob.age = 26

bob.print_age()

  

bob.birthday()

bob.print_age()

  

print(bob.name)

print(bob.age)

  

print(hasattr(bob, "age"))

print(hasattr(bob, "asd"))

  

print(getattr(bob, "age"))

  

setattr(bob, "asd", 100)

  

print(getattr(bob, "asd"))

  

delattr(bob, "asd")

  

#print(getattr(bob, "asd"))

  

print(Person.wants_to_hack)

print(bob.wants_to_hack)

print(alice.wants_to_hack)

print(sherry.wants_to_hack)

  

Person.wants_to_hack = "No way !"

  

print(Person.wants_to_hack)

print(bob.wants_to_hack)

print(alice.wants_to_hack)

print(sherry.wants_to_hack)

  

bob.wants_to_hack = "Yes way !"

  

print(Person.wants_to_hack)

print(bob.wants_to_hack)

print(alice.wants_to_hack)

print(sherry.wants_to_hack)

  

bob.print_name()

del bob.name

#bob.print_name()

  

#del Person

#print(alice.name)

  

bob2 = Person("bob2", 34)

  

print(Person.__dict__)

print(Person.__doc__)

print(Person.__name__)

print(Person.__module__)
```

## Output
```
J:\Python 201 for Hackers>python "Class,methods,objects.py"
<__main__.Person object at 0x000001A6E09C7380>
<__main__.Person object at 0x000001A6E0C55590>
<__main__.Person object at 0x000001A6E0C556D0>
My name is bob
My name is Alice
My name is Sherry
My age is 25
My age is 32
My age is 23
My age is 26
My age is 27
bob
27
True
False
27
100
True
True
True
True
No way !
No way !
No way !
No way !
No way !
Yes way !
No way !
No way !
My name is bob
{'__module__': '__main__', '__firstlineno__': 1, '__doc__': 'Person base class', 'wants_to_hack': 'No way !', '__init__': <function Person.__init__ at 0x000001A6E0C88900>, 'print_name': <function Person.print_name at 0x000001A6E0C89800>, 'print_age': <function Person.print_age at 0x000001A6E0C8B560>, 'birthday': <function Person.birthday at 0x000001A6E0CA4FE0>, '__static_attributes__': ('age', 'name'), '__dict__': <attribute '__dict__' of 'Person' objects>, '__weakref__': <attribute '__weakref__' of 'Person' objects>}
Person base class
Person
__main__
```