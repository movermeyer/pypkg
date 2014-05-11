A sample Python project
=======================

.. image:: https://travis-ci.org/dghubble/sampleproject.png
    :target: https://travis-ci.org/dghubble/sampleproject

A sample package that exists as an aid to the `Python Packaging User Guide
Tutorial<https://python-packaging-user-guide.readthedocs.org/en/latest/tutorial.html>`_ and demonstrates best practices for Python packages.

The `dghubble/sampleproject <https://github.com/dghubble/sampleproject>`_ fork customizes the sampleproject and cleans it up to my liking as a basis for my own Python packages. 

Usage
-----

0. Copy/clone sampleproject to use as the basis for a project.
1. Setup your Python package in a package directory with a matching name (e.g. package `sample` in the `sample` package directory).
2. Specify a version via :code:`__version__ = 'x.x.x'` in the package's `__init__.py` file.
3. Update `setup.py` and `setup.cfg` to correspond to the implemented package.
4. Update `requirements.txt` with dependencies. Install all dependencies into a virtualenv before starting development.
5. Remove any unneeded items from the project.
6. Develop the package locally.

::
    
    python setup.py develop      # setuptools way
    pip install -e .             # pip way

7. Write tests for the package.

::

    nosetests  # autodiscover and run tests (run from project root)

8. Write Sphinx documentation for the package.

::

    cd docs
    make html

9. Build and pack the package.

::

    python setup.py sdist        # source distribution
    python setup.py bdist        # binary distribution

10. Register the package name with `PyPI <https://pypi.python.org/pypi>`_.::

    python setup.py register

Note that registration still currently occurs over insecure http rather than https. The first attempt to connect to PyPI prompts for a username and password and generates a `.pypirc` file like the following::

    [distutils]
    index-servers =
        pypi

    [pypi]
    username:dghubble
    password:mypass

to simplify future registrations/uploads.

11. Upload the package distributions to PyPI.

::

    twine upload dist/*

12. Improve and maintain the project, docs, and tests. There is no last step. You are never done. 



