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

The ``.ninja_deps`` file in the CMake build folder is likely stale. Remove the
file, and re-run CMake configure and generate steps.

No script engine for file extension ".js"
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When configuring the project, a cscript error occurs.

.. code-block::

   Input Error: There is no script engine for file extension ".js".
   ...
   ConanException: Error 1 while executing cscript configure.js ...

This is typically caused by .js file associations. The recommended fix is to
reset the file association from the command prompt.

.. code-block::

   > assoc .js=JSFILE

Visual Studio Preview non-existing installation error
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When configuring the project using a Visual Studio Preview version, the project
fails to configure.

.. code-block::

   ConanException: VS non-existing installation: Visual Studio 17

Conan must be explicitly given the path to a Preview installation, otherwise it
will only look for release versions.

.. code-block::

   > conan profile update conf.tools.microsoft.msbuild:installation_path="C:\Program Files\Microsoft Visual Studio\2022\Preview" default

Depending on your installation method, the path to your preview installation may
vary (e.g., Community folder instead of Preview).
