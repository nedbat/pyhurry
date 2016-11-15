############
Control Flow
############

Python is a procedural language in the tradition of C, Java, and Javascript.
The control flow statements are similar.


Conditionals
============

Conditionals use ``if`` statements::

    if condition:
        do_something()
    elif another_condition:
        do_something_else()
    else:
        do_the_last_thing()

Conditions don't need parentheses around them, in keeping with Python's style
of omitting punctuation where possible.

Python has no switch statement.  Use an if/elif/elif/else ladder instead.

You can combine conditions with the ``and`` and ``or`` operators::

    if x < 0 and y < 0:
        print("lower-left quadrant!")

These short-circuit execution: if the left-hand value is enough to know the
answer, the right-hand expression isn't evaluated::

    if x == 0 or length/x > 2:
        print("some strange condition is met!")

Python's comparison operators have an unusual feature: they work as
mathematicians expect, chaining the comparison.  These two tests are equivalent::

    if 0 <= x < 10:
        print("x is in 0..9")

    if 0 <= x and x < 10:
        print("x is in 0..9")


.. todo::

    - ==, not "is".


Truthiness
==========

In Python, any value can be used as a condition:

* Numbers are considered false if they are zero, true otherwise.

* Empty strings are false, all other strings are true.

* Containers like lists, dicts, tuples, and sets are false if they are empty,
  true otherwise.


Looping
=======

Python has two looping statements: ``while`` and ``for``.  A while statement
evaluates a condition, and executes the body of the loop while the condition
is true::

    x = 0
    while x < 10:
        print(x)
        x += 1

Much more common in Python is a ``for`` statement.  It iterates over a
container, assigning each value to the loop variable, and executing the body::

    numbers = [5, 1, 3, 7]
    for num in numbers:
        print(num)

It's actually more powerful that this: ``for`` can iterate over things besides
containers. Many values in Python are iterable.  The built-in function
``range`` gives you an iterable sequence of integers::

    for i in range(5):
        print(i)

prints the numbers 0 to 4.  Like list indexes, ``range`` starts at zero and
omits the final value.

.. rst-class:: if, if_c, if_java, if_js

    There is no form of ``for`` that works as in C, Java, or Javascript.

Loops can be interrupted with the ``break`` statement, which stops the looping
immediately and carries on with the statement following the loop.  The current
iteration of the loop can be stopped with ``continue``, which will immediately
start the next iteration.
