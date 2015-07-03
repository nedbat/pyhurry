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

Combining conditions is done with the ``and`` and ``or`` operators::

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


Looping
=======

