#####
Lists
#####

A list is a complex data type that holds any number of other values, like an array.
Lists are written in square brackets, with commas separating the values.
The values can be of any type.  Unlike arrays in many other languages,
the items in the list don't have to all be the same type::

    >>> mylist = [ 1, 'hello', 17.23 ]
    >>> mylist
    [ 1, 'hello', 17.23 ]

Like strings, lists can be indexed, sliced, concatenated, and so on::

    >>> mylist[1]
    'hello'
    >>> mylist[-1]
    17.23
    >>> mylist += [ 'Cat', 'Hat' ]
    >>> mylist
    [ 1, 'hello', 17.23, 'Cat', 'Hat' ]
    >>> len(mylist)
    5
    >>> mylist[1:3]
    [ 'hello', 17.23 ]


Lists can be modified by index or slice. Assigning to a slice can change the
length of the list::

    >>> mylist
    [ 1, 'hello', 17.23, 'Cat', 'Hat' ]
    >>> mylist[1] = 'bye'
    >>> mylist
    [ 1, 'bye', 17.23, 'Cat', 'Hat' ]
    >>> mylist[1:3] = [ 2, 3 ]
    >>> mylist
    [ 1, 2, 3, 'Cat', 'Hat' ]
    >>> mylist[1:3] = [ 10, 20, 30, 40 ]
    [ 1, 10, 20, 30, 40, 'Cat', 'Hat' ]
    >>> mylist[1:5] = []
    >>> mylist
    [ 1, 'Cat', 'Hat' ]

Removing elements from a list can also be accomplished with the del statement::

    >>> mylist = [ 1, 10, 20, 30, 40, 'Cat', 'Hat' ]
    >>> del mylist[1:5]
    >>> mylist
    [1, 'Cat', 'Hat']


Lists are first-class objects with methods::

    >>> mynums = [ 106, 617, 36, 738, 41, 60 ]
    >>> mynums.reverse()        # Reverses in-place.
    >>> mynums
    [60, 41, 738, 36, 617, 106]
    >>> mynums.sort()           # Sorts in-place.
    >>> mynums
    [36, 41, 60, 106, 617, 738]

Converting between strings and lists is easy.  The string method split breaks a
string into a list of pieces.  The string method join glues together the list
elements of its argument to make a new string::

    >>> s = 'The Cat in The Hat'
    >>> s.split()
    ['The', 'Cat', 'in', 'The', 'Hat']
    >>> s.split('The')
    ['', ' Cat in ', ' Hat']

A <i>list comprehension</i> is a shorthand for creating a list.


Tuples
======

Tuples are like lists, but are immutable.  They are written with parentheses
instead of square brackets::

    >>> t = (1,2,3)
    >>> len(t)
    3
