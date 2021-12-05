# [reading-note-401](https://mohammadsilwadi.github.io/reading-note-401/)
## [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
In Python, special methods are a set of predefined methods you can use to enrich your classes. They are easy to recognize because they start and end with double underscores, for example __init__ or __str__.

As it quickly became tiresome to say under-under-method-under-under Pythonistas adopted the term “dunder methods”, a short form of “double under.”

These “dunders” or “special methods” in Python are also sometimes called “magic methods.” But using this terminology can make them seem more complicated than they really are—at the end of the day there’s nothing “magical” about them.


## Initialization of new objects
Object representation
Enable iteration
Operator overloading (comparison)
Operator overloading (addition)
Method invocation
Context manager support (with statement)
You can find the final code example here.

Object Initialization: __init__
Right upon starting my class I already need a special method. To construct account objects from the Account class I need a constructor which in Python is the ```__init__ ```dunder:

class Account:
    """A simple account class"""
```
    def __init__(self, owner, amount=0):
        """
        This is the constructor that lets us create
        objects from this class
        """
        self.owner = owner
        self.amount = amount
        self._transactions = []

```
## Object Representation: __str__, __repr__
It’s common practice in Python to provide a string representation of your object for the consumer of your class (a bit like API documentation.) There are two ways to do this using dunder methods:

__repr__: The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.

__str__: The “informal” or nicely printable string representation of an object. This is for the enduser.

## [Iterators](https://dbader.org/blog/python-iterators)
Python Iterators That Iterate Forever
We’ll begin by writing a class that demonstrates the bare-bones iterator protocol in Python. The example I’m using here might look different from the examples you’ve seen in other iterator tutorials, but bear with me. I think doing it this way gives you a more applicable understanding of how iterators work in Python.

Over the next few paragraphs we’re going to implement a class called Repeater that can be iterated over with a for-in loop, like so:

```
repeater = Repeater('Hello')
for item in repeater:
    print(item)
```


## [Generators](https://dbader.org/blog/python-generators)


Generator functions are syntactic sugar for writing objects that support the iterator protocol.

Generators abstract away much of the boilerplate code needed when writing class-based iterators.

The yield statement allows you to temporarily suspend execution of a generator function and to pass back values from it. 

Generators start raising StopIteration exceptions after control flow leaves the generator function by any means other than a yield statement.