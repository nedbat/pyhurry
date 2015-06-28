######
Basics
######


Program text
============

In Python, block structure is indicated entirely by indentation: white space
matters!  No braces, no begin/end.  This is unconventional and can be
disconcerting at first, but you get used to it.

For example, a simple function definition looks like this:

.. code-block:: python
    :linenos:

    # Compute the factorial of a number iteratively.
    def factorial(n):
        fact = 1
        while n > 0:
            fact *= n       # Multiply fact by n
            n -= 1          # Decrement n
        return fact

Comments begin with a hash mark, and continue to the end of the line.  Line 1
is a comment, and other comments appear on lines 5 and 6.  

Line 2 uses the ``def`` keyword to define a function called ``factorial`` that
takes a single argument called ``n``.  The colon introduces a series of
statements, much like an open brace in many other languages.  

Lines 3 through 7 are part of the function because they are indented farther
than line 2.  Line 3 assigns 1 to ``fact``.  No semicolon is needed to
terminate statements.

Line 4 is a while loop (no parentheses are needed around the condition), and
lines 5 and 6 are part of the while block because they are indented farther
than line 4.

Because indentation is significant, you have do it properly.  Use spaces to
indent, not tab characters.  The standard indent is 4 spaces.

Statements end at the end of the line but automatically continue onto other
lines if needed to balance matching punctuation like parentheses and brackets.
Here are two statements::

    print("Hello there.")
    print("%s %s %s" % (
        "First string",
        "Second string",
        "Third string"
        ))



Types
=====

Python is dynamically typed, meaning that any variable can be assigned any
value.  There are no type declarations.  A variable that holds an integer can
then be assigned a string, for example.

Primitive types include integers, floats, strings (both single-byte and
Unicode), and booleans (with literals True and False).  Built-in container
types include lists, dictionaries, and classes.


Interactive Interpreter
=======================

Python doesn't need a separate compilation step.  You can run the interpreter
interactively to experiment::

    $ python
    Python 3.4.1 (default, Sep 21 2014, 16:37:17)
    [GCC 4.2.1 Compatible Apple LLVM 5.1 (clang-503.0.40)] on darwin
    Type "help", "copyright", "credits" or "license" for more information.
    >>>

Python code you type at the ``>>>`` prompt is executed, and the resulting value
is displayed::

    >>> 1+2+3
    6
    >>> len("hello, world!")
    13

Most Python IDEs also provide an interpreter window with similar behavior.


Files
=====

Python is typically stored in .py files.  When executed, they are compiled as
needed into .pyc files nearby.
