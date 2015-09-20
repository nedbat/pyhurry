.. _classes:

#######
Classes
#######

Python is like many other object-oriented languages: you can create classes to
define new kinds of objects.  A class defines the things that are common to a
set of objects.  Usually, these are methods, the functions callable on objects.


Basics
======

Here's an example of a class::

    class Greeter(object):
        """Object-oriented greetings"""

        def __init__(self, name):
            self.name = name

        def greet(self, salutation="Hello"):
            print("{}, {}".format(salutation, self.name))

As with functions, classes can begin with a string literal.  This is the
docstring that documents what the class does.

Methods (functions callable on objects) are defined just like regular
functions, but indented in the body of the class.  Methods always take "self"
as a first parameter.  This will be the object the method is being called on.
Any time you want to access or update the attributes of the object, you use
"self.attr_name".  There is no "object scope" in Python: methods need to
explicitly use the self object passed to them.

.. note::

    The explicit "self" parameter on every method might seem repetitive or
    wasteful.  Other languages use an implicit reference to the object at hand.
    Python's design is simplified by using an explicit self object like this,
    though it is a little hard to quickly explain how...

You make new objects from classes by calling the class, almost as if it were
a function::

    >>> greeter = Greeter("Ned")

When a new object is made, it is initialized by calling the ``__init__`` method
on the object. ``__init__`` is pronounced "dunder init": dunder is short for
"double-underscore".  The new object is passed as self, and the arguments to
the class are passed as arguments after self.  In this case, ``name`` is equal
to "Ned".

Then you can invoke methods on the object::

    >>> greeter.greet()
    Hello, Ned

When a method is invoked, the object (in this case, greeter) is passed as
"self".  Other arguments used in the method call are passed as the rest of the
arguments to the function.  You can use defaulted and keyword arguments just as
with regular functions::

    >>> greeter.greet("Hola")
    Hola, Ned


Access control
==============

Python provides no facility for controlling access to an object's attributes.
There is no "private" or "protected", everything is public.  You may see people
talking about "__private" names, which start with two underscores.  They make
it more difficult to get at attributes, but they are not meant for this
purpose, and they don't actually prevent code from looking at your attributes.

There is a convention in Python that names starting with an underscore (like
``_name``) are not part of the public interface of a class (or module).  The
underscore doesn't stop someone from using the attribute if they are determined
to, but it provides a clear signal that they weren't meant to use it.

.. rst-class:: if, if_java, if_cpp

    Java and C++ place great importance on declaring access levels for object
    attributes.  Python doesn't have that ability.  It relies much more on
    documentation to help programmers do the right thing.


Inheritance
===========

Python classes can be created by inheriting from a base class::

    class MyClass(MyBaseClass):
        ...

Objects made from MyClass will have all of the attributes and methods defined
in MyClass, as well as all of the ones defined in MyBaseClass.  MyClass can
override methods defined in MyBaseClass simply by defining its own method with
the same name.

Python also supports multiple inheritance, where a class can have two (or
more!) base classes.  This quickly gets complicated, so use it with caution.

.. rst-class:: if, if_java

    Python has no formal notion of interfaces as Java does, though there are
    third-party packages that provide similar features.


Invoking overridden methods
===========================

If your class defines a method of the same name as a base class, you might want
to invoke the base class' definition as part of your implementation.  This is
very common in ``__init__`` methods, where you want to make sure that every
class in the inheritance chain has a chance to do its initialization.

You can't call the method directly, because ``self.__init__`` will simply call
your own method again, causing an infinite loop.  Python provides the
``super()`` function to walk up the inheritance chain to find the parent method
to call::

    class MyClass(MyBaseClass):
        def __init__(self):
            super().__init__()
            # .. do my initialization ..

or, in Python 2::

    class MyClass(MyBaseClass):
        def __init__(self):
            super(MyClass, self).__init__()
            # .. do my initialization ..

In Python 3, ``super()`` is very clever and knows what to do automatically.
In Python 2, you need to tell it explicitly what class you are calling it from,
and also what object you are working with.


Special methods
===============

Python classes can define how they interact with much of Python's built-in
syntax and machinery, by defining special methods, sometimes called magic
methods.  These are methods with dunder names: two leading underscores, and two
trailing underscores.

We've already seen ``__init__``, which is automatically invoked to initialize
new objects.  Generally, special methods are invoked by Python as it interacts
with your objects.  Don't call special methods directly, except to invoke an
overridden method in your base class.

There are dozens and dozens of special methods.  If you want your object to
behave like some built-in Python object, there is probably a special method
you can define to do it.

As an example, ``__getitem__`` is the method Python invokes when you use square
brackets with your object::

    class DictPlusOne(object):
        def __getitem__(self, key):
            return key+1

    >>> d1 = DictPlusOne()
    >>> d1[10]
    11
    >>> d1[999]
    1000
