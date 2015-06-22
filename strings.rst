#######
Strings
#######


Strings are delimited by either single quotes or double quotes: there's no
difference between the two, except that double quotes can appear unescaped in
single-quoted strings, and vice-versa.  Backslashes can be used to escape
characters and create control characters in the usual way::

    "This is a string"
    'This is a string'
    "Don't tread on me."
    'He said, "hello"'
    "Line 1\nLine2"

Strings can also begin with three single quotes or three double quotes.  This
form of string can cross lines, and the newlines are included into the string
itself.  These two strings are the same::

    """The first line.
    The second line.
    The third line."""

    'The first line.\nThe second line.\nThe third line.'


If prefixed with an r (for a raw string), then backslash escaping doesn't
apply.  This makes it easier to create strings where backslashes have meaning,
such as regular expressions.  These two strings are the same::

    r"\(hello\)"
    "\\(hello\\)"

The r prefix simply changes the escaping rules, it doesn't create a different
type.  There is no regular expression literal such as you find in Perl, Ruby,
or JavaScript.

If prefixed with a u (for Unicode), then the string is a Unicode string,
otherwise it is an single-byte string.


Substrings
==========

A single character (actually, a string of length 1) can be extracted with an
index (which starts at zero).  Substrings can be extracted with "slice"
notation for selecting a range of elements.  Two indexes are provided, the
first character to include, and the first character to not include::

    >>> s = "The Cat in The Hat"
    >>> s[0]        # Zeroth character, just a string of length 1.
    'T'
    >>> s[4:7]      # Chars 4 through 6.
    'Cat'

If you leave out the first index, it defaults to the beginning of the string.
If you leave out the second index, it defaults to the end of the string.
Negative indexes are counted from the end of the string instead of from the
beginning::

    >>> s = "The Cat in The Hat"
    >>> s[:7]       # From beginning to char 6.
    'The Cat'
    >>> s[15:]      # 15th char to the end.
    'Hat'
    >>> s[-1]       # The last character.
    't'
    >>> s[-7:]      # Seventh-to-last char through end.
    'The Hat'


String operations
=================

Strings are concatenated with the plus sign, and can be appended to with the
+= assignment statement.

    >>> s = "The Cat in The Hat"
    >>> s[4:7] + s[15:]
    'CatHat'
    >>> s += '!!!'
    >>> s
    'The Cat in The Hat!!!'

Strings are first-class objects, and have methods::

    >>> s.lower()       # Returns a new lowercased string
    'the cat in the hat'
    >>> s.upper()
    'THE CAT IN THE HAT'
    >>> s.startswith('The')
    True
    >>> s.endswith('Tin Roof')
    False
    >>> ' Hello '.strip()   # Returns it without whitespace at the ends.
    'Hello'
    >>> s.replace('at', 'op')
    'The Cop in The Hop'

The built-in function len() returns the size of a string::

    >>> len(s)
    18

The built-in function str() turns almost anything into a string::

    >>> mynum = 17
    >>> 'The value is ' + mynum
    Traceback (most recent call last):
      File "<stdin>", line 1, in ?
    TypeError: cannot concatenate 'str' and 'int' objects
    >>> 'The value is ' + str(mynum)
    'The value is 17'

Functionality similar to C's printf() is available as the % operator, which
takes a string as a left operand, and a list of values as the right operand::

    >>> mynum = 17
    >>> "The value is %d" % (mynum)
    'The value is 17'
    >>> "The value of %s is %d" % ('mynum', mynum)
    'The value of mynum is 17'
