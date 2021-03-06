===========================
 yasl |RDT| |cov|
===========================

.. |RDT| image:: https://readthedocs.org/projects/yasl/badge/?version=latest&style=flat-square
   :alt: Read-The-Docs Status
   :target: https://readthedocs.org/projects/yasl/?badge=latest

.. |cov| image:: https://img.shields.io/coverity/scan/3997.svg?style=flat-square
   :alt: Coverity Scan Status
   :target: https://scan.coverity.com/projects/3997

----------------------------------
 Yet Another String Library for C
----------------------------------

yasl is a simple dynamic string library for the C programming language,
targeting C99 and C11, and forked from the SDS library that was split out from
Redis.

Usage
=====

yasl is available to use both as a shared library and as an in-tree copy of the
library. Since there is likely no yasl package for your distribution you likely
will want to go with the second approach for now, but it would be appreciated
if your project's build system also let you use a shared library version of
yasl instead.

To use an in-tree copy of libyasl, copy the contents of the :literal:`src`
directory into your project's source tree and include the :literal:`yasl.h`
header into the files in which you want to use yasl, and compile
:literal:`yasl.c` into your program.

To link to libyasl as a shared library just include the :literal:`yasl.h`
header in the files in which you want to use yasl, and then either use
`pkg-config` like::

    pkg-config --cflags --libs libyasl

or link your program directly against :literal:`libyasl`.

Building
========

To build libyasl make sure the following dependencies are installed:

  * meson
  * ninja
  * sphinx-build

Following are an example build and installation using meson::

    mkdir build
    meson build --prefix=/usr
    cd build
    ninja
    DESTDIR=/destination ninja install

Testing
=======

The yasl test suite is compiled with C99 and written using twbctf_.

To compile and run the test suite, run the following command::

    mkdir build
    meson build
    cd build
    ninja test

.. _twbctf: https://github.com/HalosGhost/twbctf

Documentation
=============

The new API documentation for yasl can either be found in ``docs/API.rst``, or
a built HTML version `here <http://yasl.readthedocs.org/en/latest/>`_. The API
documentation is very new and might not be as accurate as it should and also
does not yet have small code examples, though this is a planned addition.

For code examples the best sources right now is the tests in ``test/tests.c``
and in the old SDS README which can be found in ``docs/README.md.sds``.

Contributing
============

1. Check for `open issues`_ or open a `new issue`_ to start a discussion around
   a feature idea or a bug.

2. Fork `the repository on GitHub <https://github.com/yabok/yasl>`_ to start
   making your changes.

3. Write one or more tests which shows that the bug was fixed or that the
   feature works as expected.

4. Send a pull request and bug the maintainers until it gets merged.

.. _`open issues`: https://github.com/yabok/yasl/issues
.. _`new issue`: https://github.com/yabok/yasl/issues/new

License
=======

Every file in this repository, except for as otherwise specified in the file
itself or in this README if not possible, is licensed under a 2-clause BSD
license.
