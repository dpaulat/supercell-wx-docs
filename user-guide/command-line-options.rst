====================
Command Line Options
====================

Overview
========

Supercell Wx accepts several command line options that can be used to modify the behavior of the application. These options can be used to enable console output, run the application in portable mode, or specify a custom settings directory. These options can be used either when launching Supercell Wx via the command line, or by adding them to a shortcut or application launcher.

----

.. code-block:: none

   Supercell Wx - Free and open source advanced weather radar

   Usage:
   supercell-wx [qt options] [options]

   Options:
   -h [ --help ]             Display this help message
   -c [ --console ]          Enable console output
   -p [ --portable ]         Run in portable mode, storing settings in the
                             application directory
   --settings-directory path Override the default settings directory with the
                             specified path

   Qt Options:
     Qt platform and UI options (e.g., -style, -platform, -geometry)
     may also be specified. These are consumed by the Qt framework
     before application argument parsing and are not listed here.
     See https://doc.qt.io/qt-6/qapplication.html for details.
