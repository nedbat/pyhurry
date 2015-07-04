#####
Lists
#####

A list is a data type that holds any number of other values as an ordered sequence.
Other languages call similar structures arrays or vectors.
Lists are written in square brackets, with commas separating the values.
The values can be of any type.  Unlike arrays in many other languages,
the items in the list don't have to all be the same type:

.. doctest::

    >>> mylist = [ 17, 'hello', 3.14159 ]
    >>> mylist
    [17, 'hello', 3.14159]

Like strings, lists can be indexed, sliced, concatenated, and so on:

.. doctest::

    >>> mylist[1]
    'hello'
    >>> mylist[-1]
    3.14159
    >>> mylist += [ 'Cat', 'Hat' ]
    >>> mylist
    [17, 'hello', 3.14159, 'Cat', 'Hat']
    >>> len(mylist)
    5
    >>> mylist[1:3]
    ['hello', 3.14159]

Lists can be modified by index. Remember that the first element is index 0:

.. doctest::

    >>> mylist
    [17, 'hello', 3.14159, 'Cat', 'Hat']
    >>> mylist[1] = 'bye'
    >>> mylist
    [17, 'bye', 3.14159, 'Cat', 'Hat']

Or lengthened:

.. doctest::

    >>> mylist.append("More")
    >>> mylist
    [17, 'bye', 3.14159, 'Cat', 'Hat', 'More']
    >>> mylist.extend([99, 100, 101])
    >>> mylist
    [17, 'bye', 3.14159, 'Cat', 'Hat', 'More', 99, 100, 101]

Notice that the `append` and `extend` methods don't return anything.  This is
common in Python: methods that modify the object directly don't return the
object.

Lists are first-class objects with methods:

.. doctest::

    >>> mynums = [ 106, 617, 36, 738, 41, 60 ]
    >>> mynums.reverse()        # Reverses in-place.
    >>> mynums
    [60, 41, 738, 36, 617, 106]
    >>> mynums.sort()           # Sorts in-place.
    >>> mynums
    [36, 41, 60, 106, 617, 738]

Converting between strings and lists is easy.  The string method ``s.split()``
breaks a string into a list of pieces based on white space.  The string method
``sep.join(list)`` glues together the list elements of its argument to make a
new string:

.. doctest::

    >>> s = 'The Cat in The Hat'
    >>> parts = s.split()
    >>> parts
    ['The', 'Cat', 'in', 'The', 'Hat']
    >>> ":".join(parts)
    'The:Cat:in:The:Hat'

.. todo::

    A list comprehension is a shorthand for creating a list.


Tuples
======

Tuples are like lists, but are immutable.  They are written with parentheses
instead of square brackets:

.. doctest::

    >>> t = (1, 2, 3)
    >>> len(t)
    3

Being immutable means that once created, they cannot be changed:

.. doctest::

    >>> t[1] = 17
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: 'tuple' object does not support item assignment
    >>> t.append(43)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    AttributeError: 'tuple' object has no attribute 'append'
    >>>

Because parentheses are used for grouping also, a single-element tuple needs a
trailing comma:

.. doctest::

    >>> (1)
    1
    >>> (1,)
    (1,)
    >>>

It's actually the commas that make the tuple, not the parentheses:

.. doctest::

    >>> 1, 2, 3
    (1, 2, 3)
    >>>


Iteration
=========

Lists and tuples are ordered: there is a first element, a second element, and
so on.  The ``for`` statement in Python is good at processing all of the
elements of a list in order::

    my_data = [1, 7, 10]
    for x in my_data:
        print(my_data)

Here ``x`` is assigned each element of the list in turn, and then the body of
the for loop is executed.

Python provides many other ways to iterate over sequences like lists:

.. doctest::

    >>> numbers = [5, 1, 3, 9, 7]
    >>> sum(numbers)
    25
    >>> min(numbers)
    1
    >>> max(numbers)
    9
