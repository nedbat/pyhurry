############
Dictionaries
############

Dictionaries (or dicts for short) are containers of key/value pairs.  Other
languages call them by other names, like hashmaps, hashes, or associative
arrays.

Dictionaries are written with curly braces.  You can create one with certain
keys and values directly::

    d = {
        'name': 'Joe',
        'age': 35,
    }

Here the key ``'name'`` maps to the string ``'Joe'``, and the key ``'age'``
maps to the integer 35.  As with the rest of Python, there is no type
enforcement. It's fine for the values to be of different types.  It's also
possible to use different types for keys, but usually they are strings.

Once you have a dictionary, you can index into it to look up the value for a
key::

    >>> d['name']
    'Joe'
    >>> d['age']
    35

You can assign to a key, either to create a new key or to change the value of
an existing key::

    >>> d['age'] = 36       # Happy Birthday!
    >>> d['height'] = 71
    >>> d
    {'height': 71, 'name': 'Joe', 'age': 36}

Notice that when we printed the dict, the keys appeared in a different order
than we assigned them.  Dicts have no order.  There is no "first" key. When
you iterate over the items in a dict, they are in an arbitrary order.

.. todo::

    key in dict

    iterating over keys
