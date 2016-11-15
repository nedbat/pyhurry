#############
Preliminaries
#############

Before jumping into Python as a language, let's get a few things out of the way.


Python 2 or Python 3?
=====================

There are two major versions of Python: 2.x and 3.x.  They are incompatible:
Python 2 code will not run in a Python 3 interpreter.  So you have
to choose which to use.  In the past, this has been a difficult and 
contentious choice.

The good news is that the two languages are 95% the same, so whichever you
choose to learn, you have almost completely learned the other.

To choose between Python 2 and 3, you should consider what you are going to be
building, and determine which provides you with all of what you need.  Then
choose the highest version number that satisfies all your requirements.  Here
are some things to consider:

* Third-party libraries.  In the past, this has been the difficulty with Python
  3: too many libraries only supported Python 2.  This is usually no longer a
  problem, but double-check your requirements to be sure.

* Existing code. If you are joining a project already in progress, they may
  have already made the choice for you.

* Smaller considerations: hosting options, learning resources, skills among
  collaborators, and so on.

For the most part, this tutorial will use Python 3.  Sometimes I'll point out
a difference between Python 2 and 3, and will highlight the version-specific
code examples.
