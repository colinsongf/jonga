Jonga
=====

Jonga is a Python package that generates a directed graph representing
function calls within a block of Python code, intended for inclusion
in Sphinx package documentation. There are a number of
alternative packages with similar goals, including

* `pycallgraph <https://github.com/gak/pycallgraph>`_
* `pyan <https://github.com/davidfraser/pyan>`_
* `snakefood <https://bitbucket.org/blais/snakefood/src>`_

but none of them is entirely suitable for generating function/method call
vizualizations for inclusion within package documentation. In
particular, none of these other packages correctly identifies method
classes within a hierarchy of derived classes.



Requirements
------------

The primary requirement is Python 3.3 or greater (this packages is
*not* compatible with Python 2), imposed by the use of the
``__qualname__`` function attribute and `inspect.getclosurevars
<https://docs.python.org/3/library/inspect.html#inspect.getclosurevars>`_.
The ``__qualname__`` attribute could be replaced in earlier versions
of Python by `qualname <https://github.com/wbolster/qualname>`_, but
there is no obvious replacement for `inspect.getclosurevars
<https://docs.python.org/3/library/inspect.html#inspect.getclosurevars>`_,
which was introduced in Python 3.3.

The other major requirement is `pygraphviz <https://pygraphviz.github.io/>`_.


Optional
^^^^^^^^

Packages `pytest <https://github.com/pytest-dev/pytest>`_ and
`pytest-runner <https://github.com/pytest-dev/pytest-runner>`_ are
required to run the tests (``python setup.py test`` or ``python3
setup.py test``, depending on the operating system). Packages `sphinx
<http://www.sphinx-doc.org/en/stable>`_ and `sphinx-bootstrap-theme
<http://ryan-roemer.github.io/sphinx-bootstrap-theme/README.html>`_
are required to build the documentation (``python setup.py
build_sphinx`` or ``python3 setup.py build_sphinx``, depending on the
operating system).



Usage
-----

Scripts illustrating usage of the package can be found in the
``examples`` directory of the source distribution. These examples can
be run from the root directory of the package by, for example

::

   python3 examples/example1.py


To run these scripts prior to installing the package it will be
necessary to first set the ``PYTHONPATH`` environment variable to
include the root directory of the package. For example, in a ``bash``
shell

::

   export PYTHONPATH=$PYTHONPATH:`pwd`


from the root directory of the package.



License
-------

This package is made available under the terms of the GNU General
Public License as published by the Free Software Foundation; either
version 2 of the License (see the included ``LICENSE.rst`` file), or
(at your option) any later version.