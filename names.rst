##############
Names & Values
##############


Names
=====

Python's variables are names that refer to values.  Names have no type, and
there are no variable declarations.  Names are created by assigning a value to
them::

    x = "value"

The left-hand side of assignment statements can have simple names, object
attributes, and elements of containers::

    name = "value"
    name.attribute = "value"
    container[key] = "value"
    container[key].attribute[index].attribute = "value"
    # etc...

Because names are not typed, they can be assigned new values with a different
type than their old value::

    x = 1
    x = "hello"     # This is fine.

This untyped nature of names is true of all of the targets of assignment
statements.  Generally, where Python can accept a value, it will accept any
type of value.


Values & Types
==============

All values in Python are objects (more about that later).  Every value has a
definite type.

Python has a rich set of built-in types:

    * Numbers, including unlimited precision integers, double-precision floats,
      and complex numbers.

    * Booleans, with constants ``True`` and ``False``.

    * A special value, ``None``, used when no other value is appropriate.

    * Strings, both byte strings and Unicode strings (see :ref:`strings`).

    * Containers like lists (see :ref:`lists`) and dictionaries (see
      :ref:`dicts`).

    * User-defined objects (see :ref:`classes`).

In addition to these conventional data types, in Python many things that you
might not expect are first-class values, like functions, classes, and modules.
These can be manipulated just like other values, assigning them to names,
passing them to functions, and storing them in containers. 


Assignment
==========

Assignment statements make names refer to values.  The value itself is never
copied.  Two names can refer to the same value, and when it changes, both names
see the change:

.. doctest::

    >>> nums = [1, 2, 3]
    >>> saved = nums        # Not really saved...
    >>> nums.append(4)
    >>> nums
    [1, 2, 3, 4]
    >>> saved
    [1, 2, 3, 4]


Assignment statements inside functions make names local to the function. The
scope a name is the entire function.  There is no block-level scope.

If you want to assign to a name outside of the function, you use the ``global``
statement, which indicates that the name is global even though it's being
assigned a value inside a function::

    total = 0

    def add_another():
        global total
        total += 1

Augmented assignment statements are available for updating the value of a
name::

    x += 1      # x = x + 1
    y *= 2      # y = y * 2

You can chain assignments together to assign the same value to more than one
name:

    a = b = c = 0

You can also assign a number of values to a number of names at once. These
assignment statements have the same effect::

    x, y = 1, 2

    x = 1
    y = 2

except that the left-hand sides are fully evaluated, and then the names are
assigned.  You can swap variables like this::

    x, y = y, x


.. rst-class:: if, if-c

    Assignment in Python is a statement, not an expression.  This means that
    you cannot use assignment where expressions are needed.  For example, you
    cannot assign to a name and test a value at once as in this C code::

        while (name = next_value()) {
            do_something_with(name);
        }
