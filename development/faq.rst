Frequently Asked Questions
==========================

.. contents::
   :local:

Build issues
------------

Ninja build crashes with error 0xC0000005
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When compiling using the Ninja generator, an error occurs during compilation.

.. code-block::

   ninja: error: exception: 0xC0000005
   ninja: warning: minidump created: <path>

The ``.ninja_deps`` file in the CMake build folder is likely stale. Remove the file, and re-run CMake configure and generate steps.
