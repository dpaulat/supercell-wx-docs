Developer Setup
===============

Required Tools
--------------

- Compiler

  - Windows

    - `Microsoft Visual Studio 2022 <https://visualstudio.microsoft.com/downloads/>`_

  - Linux

    - GCC/G++ >= 11
    - Ninja (ninja-build) recommended

- `CMake >= 3.21 <https://cmake.org/download/>`_
- `Git <https://git-scm.com/download/win>`_
- `Python >= 3.10 <https://www.python.org/downloads/windows/>`_
- `Qt 6.8.0 <https://www.qt.io/download-open-source>`_

  - For Microsoft Visual Studio >= 2019, install Qt for **MSVC 2019 64-bit**
  - For Linux GCC, install Qt for **Desktop gcc 64-bit**
  - Additional libraries

    - Qt Image Formats
    - Qt Multimedia
    - Qt Positioning
    - Qt Serial Port

    .. image:: images/developer-setup-01-qt-install-small.png

  - See setup-* scripts for current version
  - Add the ``bin`` directory to your system ``PATH`` variable (e.g., ``C:\Qt\6.8.0\msvc2019_64\bin``)
  - Alternate install via aqtinstall (installs to a versioned subdirectory
    within the current directory)

    .. code:: bash

      > pip install --upgrade aqtinstall
      > aqt install-qt windows desktop 6.8.0 win64_msvc2019_64 -m qtimageformats qtmultimedia qtpositioning qtserialport
      > aqt install-qt linux desktop 6.8.0 linux_gcc_64 -m qtimageformats qtmultimedia qtpositioning qtserialport

    - See https://ddalcino.github.io/aqt-list-server/ for additional configurations

.. note:: Qt versions maintain a level of compatibility between patch releases
          of the same major and minor versions (e.g., 6.8.0 through 6.8.3). No
          issues are expected moving between patch releases. Breaking changes
          may sometimes be introduced in minor releases (e.g., 6.8 to 6.9). As
          new releases become available, older releases should remain available
          via the Archive selection filter in the Qt Maintenance Tool or via
          aqtinstall.

Recommended Tools
-----------------

Integrated Development Environment
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

An IDE is strongly recommended to develop Supercell Wx. `Microsoft Visual Studio
<https://visualstudio.microsoft.com/downloads/>`_ is a good option on Windows,
and `Visual Studio Code <https://code.visualstudio.com/>`_ is a good
cross-platform option.

For Visual Studio Code, it is recommended to install the following extensions:

- `C/C++ Extension Pack <https://marketplace.visualstudio.com/items?itemName=ms-vscode.cpptools-extension-pack>`_
- `Python <https://marketplace.visualstudio.com/items?itemName=ms-python.python>`_
- `reStructuredText <https://marketplace.visualstudio.com/items?itemName=lextudio.restructuredtext>`_
- `reStructuredText Syntax highlighting <https://marketplace.visualstudio.com/items?itemName=trond-snekvik.simple-rst>`_
- `SQLite Viewer <https://marketplace.visualstudio.com/items?itemName=qwtel.sqlite-viewer>`_

For remote development (e.g., Linux development on a Windows host), it is also
recommended to install the following:

- `Remote Development <https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack>`_

For UI development, it is recommended to run Qt Creator, installable via the Qt
Maintenance Tool or aqtinstall. Alternatively, Qt Designer may be used as a
lighter weight option.

.. note:: Qt Creator has had issues building the Supercell Wx project, with
          infinite recursion during CMake and Conan configuration, and is
          therefore only recommended for UI development. These issues may have
          since been resolved, but your mileage may vary.

Other IDEs are likely to work as well, however, the following have not been tested:

- `Code::Blocks <https://www.codeblocks.org/>`_
- `CLion <https://www.jetbrains.com/clion/>`_
- `Eclipse IDE for C/C++ Developers <https://www.eclipse.org/downloads/packages/installer>`_

Git Tools
^^^^^^^^^

A visual tool for navigating the Git repository and submodules can be helpful,
but is not required for development.

- `GitKraken <https://www.gitkraken.com/>`_
- `GitLens <https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens>`_
- `Sourcetree <https://www.sourcetreeapp.com/>`_

Initial Configuration
---------------------

After cloning the repository from `GitHub <https://github.com/dpaulat/supercell-wx>`_, initialize all submodules:

.. code:: bash

  > git submodule update --init --recursive

It is recommended to run the initial CMake configure and generate steps via the
provided setup scripts. View the ``setup-{config}.{ext}`` contents, and make any
changes required for your environment, including desired build directory and Qt
path. Alternatively, you can let your IDE configure for you (e.g., Visual Studio
Code), although ensure you include the proper CMake variables (-D) when
configuring.

.. note:: CMake multi-config (i.e., single build directory for Debug and
          Release) is currently not supported. This is expected to be supported
          upon migration to Conan 2.x.

Using the default setup scripts, CMake will generate Visual Studio solution
files for Windows, and Ninja build files for Linux. To change this behavior, add
or modify the ``-G`` parameter with the appropriate CMake generator.

If configuring manually instead of using a provided setup script (e.g., with
Visual Studio Code on Windows), it is recommended to at least run
``tools/setup-common.{ext}``. This will ensure Python dependencies are setup
properly, as well as your conan profile.

When configuring on Linux, you may encounter an error due to missing packages
from your system. These may be installed manually, or you may update your conan
global configuration (``~/.conan/global.conf``):

.. code::

    tools.system.package_manager:mode = install
    tools.system.package_manager:sudo = True

After installing missing packages, re-run the setup script.

.. note:: After updating compiler or Qt versions, you may need to update paths
          in your CMake cache. This may be done via your IDE, or by manually
          editing CMakeCache.txt located in your build directory.

Visual Studio
^^^^^^^^^^^^^

When CMake is run with the Visual Studio generator, your build directory will
contain a ``supercell-wx.sln`` file. Open this in Visual Studio, and proceed to
build the supercell-wx target.

Visual Studio Code
^^^^^^^^^^^^^^^^^^

Open the supercell-wx source directory in Visual Studio Code. Open the Settings
Window, and filter on CMake. In Workspace settings, set your Build Directory to
your desired destination.

.. image:: images/developer-setup-02-vscode-cmake-build-dir.png

On the Primary Side Bar (left), select the CMake icon. Under Build, select the
appropriate Kit (compiler), and set your target to supercell-wx. You can proceed
to build supercell-wx using the ``Build`` button on the left side of the Status
Bar.

Guidelines
----------

It is expected that developers will follow these guidelines. On occasion, there
will be use cases for deviation from the guidelines below.

- Don't break existing functionality
- Follow C++ best practices
- Format files after making changes (most IDEs will respect the .clang-format
  file at the root of the repository)
- Follow the `Google C++ Style Guide <https://google.github.io/styleguide/cppguide.html>`_
- Keep Qt-dependent code in the ``scwx-qt`` project
- If adding a dependency, prefer adding it to conanfile.py over adding a
  submodule, unless additional customization is necessary
- Minimize custom development environment configuration
- Update acknowledgements when appropriate

  - Supercell Wx should remain MIT-licensed
  - Dependencies must be compatible with the MIT license

    - LGPL-licensed software must be contained within shared libraries
    - GPL-licensed software must not be used

Help
----

Stuck? You can look at https://github.com/dpaulat/supercell-wx/blob/develop/.github/workflows/ci.yml
for hints, or join the Discord server for help.
