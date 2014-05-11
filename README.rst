A sample Python project
=======================

A sample project that exists as an aid to the `Python Packaging User Guide
Tutorial<https://python-packaging-user-guide.readthedocs.org/en/latest/tutorial.html>`_ and demonstrates best practices for Python packages.

1. Create your package directory in the project directory.
2. Specify the `__version__ = 'x.x.x'` in the package `__init__.py` file.
3. Update the setup.py file with information about the package.
4. Remove files/code that is not needed.
5. Develop the package locally.

::
    
    python setup.py develop      # setuptools way
    pip install -e .             # pip way

6. Write tests for the package.
7. Write documentation for the package.
8. Build and pack the package.

::

    python setup.py sdist        # source distribution
    python setup.py bdist_wheel  # binary distribution

9. Upload the package to `PyPi <https://pypi.python.org/pypi>`_.

    twine upload dist/*


