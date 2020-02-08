pl-chris-matrix-multiply
================================

.. image:: https://badge.fury.io/py/chris_matrix_multiply.svg
    :target: https://badge.fury.io/py/chris_matrix_multiply

.. image:: https://travis-ci.org/FNNDSC/chris_matrix_multiply.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/chris_matrix_multiply

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pl-chris_matrix_multiply

.. contents:: Table of Contents


Abstract
--------

An app to ...


Synopsis
--------

.. code::

    python chris_matrix_multiply.py                                           \
        [-v <level>] [--verbosity <level>]                          \
        [--version]                                                 \
        [--man]                                                     \
        [--meta]                                                    \
        <inputDir>
        <outputDir> 

Description
-----------

``chris_matrix_multiply.py`` is a ChRIS-based application that...

Agruments
---------

.. code::

    [-v <level>] [--verbosity <level>]
    Verbosity level for app. Not used currently.

    [--version]
    If specified, print version number. 
    
    [--man]
    If specified, print (this) man page.

    [--meta]
    If specified, print plugin meta data.


Run
----

This ``plugin`` can be run in two modes: natively as a python package or as a containerized docker image.

Using PyPI
~~~~~~~~~~

To run from PyPI, simply do a 

.. code:: bash

    pip install chris_matrix_multiply

and run with

.. code:: bash

    chris_matrix_multiply.py --man /tmp /tmp

to get inline help. The app should also understand being called with only two positional arguments

.. code:: bash

    chris_matrix_multiply.py /some/input/directory /destination/directory


Using ``docker run``
~~~~~~~~~~~~~~~~~~~~

To run using ``docker``, be sure to assign an "input" directory to ``/incoming`` and an output directory to ``/outgoing``. *Make sure that the* ``$(pwd)/out`` *directory is world writable!*

Now, prefix all calls with 

.. code:: bash

    docker run --rm -v $(pwd)/out:/outgoing                             \
            fnndsc/pl-chris_matrix_multiply chris_matrix_multiply.py                        \

Thus, getting inline help is:

.. code:: bash

    mkdir in out && chmod 777 out
    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing      \
            fnndsc/pl-chris_matrix_multiply chris_matrix_multiply.py                        \
            --man                                                       \
            /incoming /outgoing

Examples
--------





