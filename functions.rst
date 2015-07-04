#########
Functions
#########


If you've used functions in other languages, Python's functions will be
familiar.


Defining Functions
==================

You define functions with the ``def`` keyword::

    def my_function(arg1, arg2):
        arg1 *= 2
        return arg1 + arg2

    print(my_function(100, 17))     # Prints 217

The function name and the formal parameters are defined, then the body of the
function is indented underneath.

When a function is called, the actual arguments are assigned to the formal
parameters, and the statements in the body of the function are executed.

A ``return`` statement ends execution of the function and provides a value
back to the caller.  Python functions always return a value.  If the function
ends with no return statement, then the return value is ``None``.

.. rst-class:: if, if_c, if_java

    Python has no means of overloading a name. You can only have one function
    for each name.

.. rst-class:: if, if_ruby

    Unlike Ruby, you must use parentheses to call functions.  A function name
    with parentheses simply refers to the function as an object.


Defaults
========

You can give functions flexible calling signatures by using defaulted
parameters.  If a formal parameter is given a value in the function definition,
then that value is used if a value isn't provided when the function is called::

    def scale_up(width, factor=2):
        return width*factor

    print(scale_up(100, 3))     # factor == 3, result is 300
    print(scale_up(100))        # factor == 2, result is 200

Here we can call ``scale_up`` with two arguments, providing all values
explicitly, or with only one argument.  The ``factor`` argument has a default
of 2 which is used in the one-argument call.


Calling Functions
=================

When you call a function, the actual arguments are paired with formal
parameters positionally: the first argument is assigned to the first parameter,
and so on.

But you can also name the parameter explicitly in the function call. This is
known as a keyword argument, and is useful when there are multiple parameters
with default arguments::

    def make_text_box(text, width=100, height=50, color='white'):
        ...

    make_text_box("Hello")
    make_text_box("narrow", width=20)
    make_text_box("alarming", color="red")


Functions as Values
===================

Functions are first-class values in Python, meaning they can be assigned to
names, passed as arguments, and stored in containers.

As an example, the ``sorted()`` built-in function produces a sorted list from
its sequence argument.  It has a ``key`` argument that accepts a function.  It
will use the function to compute the sort key for each item in the sequence.

.. testcode::

    def third_letter(s):
        return s[2]

.. doctest::

    >>> names = ["Sarina", "James", "Diana", "Rob"]
    >>> sorted(names, key=third_letter)
    ['Diana', 'Rob', 'James', 'Sarina']

The name ``third_letter`` refers to the function we defined.  That function
can be passed as an argument to the ``sorted`` function.


Lambdas
=======

Python has anonymous functions, created with the ``lambda`` keyword.  We can
rewrite the ``third_letter`` example like this:

.. doctest::

    >>> sorted(names, key=lambda s: s[2])
    ['Diana', 'Rob', 'James', 'Sarina']

A lambda can take arguments just like a regular function, but its body is only
a single expression.  These two functions do the same thing::

    lambda ARGS: EXPR

    def function_name(ARGS):
        return EXPR

Lambdas are useful when passing a function to another function. Don't overuse
them.

.. rst-class:: if, if_javascript

    There is no multi-statement syntax for anonymous functions in Python.


.. todo::

    - ``*args, **kwargs``?
