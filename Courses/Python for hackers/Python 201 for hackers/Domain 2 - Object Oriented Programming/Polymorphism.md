___
## Input
```
class Person:

    'Person base class'

    wants_to_hack = True

  

    def __init__(self, name, age):

        self.name = name

        self.age = age

  

    def print_name(self):

        print("My name is {}".format(self.name))

  

    def print_age(self):

        print("My age is {}".format(self.age))

  

    def birthday(self):

        self.age += 1

  

class Hacker(Person):

    def __init__(self, name, age, cves):

        super().__init__(name, age)

        self.cves = cves

  

    def print_name(self):

        print("My name is {} and I have {} CVEs".format(self.name, self.cves))

  

    def total_cves(self):

        return self.cves

bob = Person("bob", 30)

alice = Hacker("alice", 34, 10)

people = [bob,alice]

  

for person in people:

    person.print_name()

    print(type(person))

  

def obj_dump(object):

    object.print_name()

    print(object.age)

    object.birthday()

    print(object.age)

    print(object.__class__)

    print(object.__class__.__name__)

  

obj_dump(bob)

obj_dump(alice)
```

## Input
```
J:\Python 201 for Hackers>python Polymorphism.py
My name is bob
<class '__main__.Person'>
My name is alice and I have 10 CVEs
<class '__main__.Hacker'>
My name is bob
30
31
<class '__main__.Person'>
Person
My name is alice and I have 10 CVEs
34
35
<class '__main__.Hacker'>
Hacker
```

