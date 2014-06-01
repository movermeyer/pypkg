Pypkg
=====

.. image:: https://pypip.in/version/pypkg/badge.png
    :target: https://pypi.python.org/pypi/pypkg/
    :alt: Latest Version

.. image:: https://travis-ci.org/dghubble/pypkg.png
    :target: https://travis-ci.org/dghubble/pypkg
    :alt: Continuous Integration Testing

.. image:: https://pypip.in/download/pypkg/badge.png
    :target: https://pypi.python.org/pypi/pypkg/
    :alt: Downloads

.. image:: https://pypip.in/license/pypkg/badge.png
    :target: https://pypi.python.org/pypi/pypkg/
    :alt: License

A sample package that exists as an aid to the `Python Packaging User Guide
Tutorial <https://python-packaging-user-guide.readthedocs.org/en/latest/tutorial.html>`_ and demonstrates best practices for Python packages. This fork has been customized to suit my own preferences.


Getting Started
---------------

0. Copy/clone `Pypkg` to use as the basis for your project.
1. Setup your Python package in a package directory with a matching name (e.g. package `pypkg` in the `pypkg` package directory).
2. Set the package version `x.x.x` in the package's `VERSION` file.
3. Update `setup.py` and `setup.cfg` with the name, dependencies, etc. of your package.
4. Install development dependencies into a virtual environment and list them in `requirements.txt`.
5. Develop the package locally.

::
    
    python setup.py develop      # setuptools way
    pip install -e .             # pip way

6. Write tests for the package and ensure the .travis.yml config will run them.

::

    nosetests  # autodiscover and run tests (run from project root)

7. Write Sphinx documentation for the package.

::

    cd docs
    make html


Checklist
---------

After making development changes, use this checklist:

- Local nosetests pass
- Continuous Integration tests pass (sandbox)
- Changes are summarized in `CHANGES.rst`
- Increment the version in `pypkg/VERSION`


Publishing
----------

1. Create a new repository on a source host such as Github or Bitbucket.
2. Go to `Travis CI <https://travis-ci.org/>`_ or another CI runner and setup your repository.
3. Update the badge links in the project `README.rst`.
4. Push the source to your repository host.
5. Go to `ReadTheDocs <https://readthedocs.org/>`_ and build your docs from the hosted source.
6. Build and pack the package.

::

    python setup.py sdist        # source distribution
    python setup.py bdist        # binary distribution

7. Register the package name with `PyPI <https://pypi.python.org/pypi>`_.::

    python setup.py register

Note that registration still currently occurs over insecure http rather than https. The first attempt to connect to PyPI prompts for a username and password and generates a `.pypirc` file like the following::

    [distutils]
    index-servers =
        pypi

    [pypi]
    username:dghubble
    password:mypass

to simplify future registrations/uploads.

8. Upload the package distributions to PyPI.

::

    twine upload dist/*

9. Check all README.rst links, documentation links, and PyPI links for correctness.
10. Improve and maintain the project, docs, and tests. There is no last step. You are never done.


Example
=======

Install
-------

Install pypkg via `pip <https://pip.pypa.io/en/latest/>`_

.. code-block:: bash

    $ pip install pypkg

Usage
-----

.. code-block:: bash

    $ pypkg
    ~Call your main application code here~

.. code-block:: pycon

    >>> from pypkg.core import fancy_print
    >>> fancy_print("hello world")
    ~hello world~

Documentation
-------------

Documentation is available `here <http://pypkg.readthedocs.org/en/latest/>`_.


Contributing
------------

To get the source from Github

.. code-block:: bash

    $ git clone git@github.com:dghubble/pypkg.git
    $ cd pypkg
    $ python setup.py develop


Testing
-------

.. code-block:: bash

    $ pip install nose
    $ cd pypkg
    $ nosetests
    ....
    ----------------------------------------------------------------------
    Ran 4 tests in 0.147s

    OK


Questions, Comments, Contact
----------------------------

If you'd like to contact me, you can Tweet to `@dghubble <https://twitter.com/dghubble>`_ or email dghubble@gmail.com.


License
-------

`MIT License <LICENSE>`_ 



