.. _thirdparty:

#################
Third-Party Tools
#################


Python has a large standard library, providing many useful modules right out of
the box.  But it will never have everything you need.  Python also has a huge
collection of third-party modules available for you to install.


pip
===

Python comes with a package manager called pip.  The name is a recursive
acronym short for Pip Installs Packages.

If you're using a recent version of Python 3 (3.4 or higher), then you already
have a pip3 command that will install packages.

If you've installed Python 2.7.10, and you don't have a pip command, you can
install one by running::

    $ python2.7 -m ensurepip

Installing packages is as easy as::

    $ pip install the_package_name

If you have more than one installation of Python on your machine, be sure you
know which pip (or pip3) you are using.  Pip will install packages into the
Python installation you run it from.


PyPI
====

Python packages are available from the Python Package Index, or `PyPI`_,
pronounced Pie-Pee-Eye.  Pip automatically knows to install from PyPI, but you
can manually search or browse PyPI if you need to.


Virtualenv
==========

Virtualenv is a third-party tool for isolating Python package installations
from each other.  If you are working on more than one project, it's a good
practice to keep their package requirements separate.  Virtualenv lets you
create a virtual Python environment for each project, and install packages
separately for each.

.. todo:: find good instructions to link to for virtualenv.


Popular third-party libraries
=============================

PyPI has thousands of packages, it would be impossible to summarize them all.
But there are a handful of go-to packages that many people use for common
tasks:

* requests

* scrapy

* Twisted

* Pillow

* lxml

* PyYAML

* Django, Flask, Pyramid

* SQLAlchemy

* numpy, scipy, pandas

* pytest, tox, coverage, mock

* six

* Jinija2

* cryptography

* pylint, flake8, pep8

* pymongo, redis, MySQL-Python, psycopg2


.. _PyPI: http://pypi.python.org/
