====================
Command Line Options
====================

Overview
========

Supercell Wx accepts several command line options that can be used to modify the
behavior of the application. These options can enable console output, run the
application in portable mode, specify a custom settings directory, or select
alternate Level 2 and Level 3 radar data providers. Options can be used when
launching Supercell Wx from the command line, or by adding them to a shortcut or
application launcher.

----

.. code-block:: none

   Supercell Wx - Free and open source advanced weather radar

   Usage:
   supercell-wx [qt options] [options]

   Options:
   -h [ --help ]             Display this help message
   -c [ --console ]          Enable console output
   --level2-provider url     Level 2 data provider URL. Protocol may be any of:
                             HTTP/HTTPS (ONDAS), or S3.
   --level3-provider url     Level 3 data provider URL. Protocol may be any of:
                             HTTP/HTTPS (ONDAS or TGFTP), or S3.
   -p [ --portable ]         Run in portable mode, storing settings in the
                             application directory
   --settings-directory path Override the default settings directory with the
                             specified path

   Qt Options:
     Qt platform and UI options (e.g., -style, -platform, -geometry)
     may also be specified. These are consumed by the Qt framework
     before application argument parsing and are not listed here.
     See https://doc.qt.io/qt-6/qapplication.html for details.

Data Provider Options
=====================

By default, Supercell Wx downloads NEXRAD Level 2 and Level 3 data from AWS S3
(``unidata-nexrad-level2`` and ``unidata-nexrad-level3``). Use
``--level2-provider`` and ``--level3-provider`` to override these defaults with
an alternate source.

Supported URL schemes
---------------------

.. list-table::
   :header-rows: 1
   :widths: 20 35 45

   * - Scheme
     - Level 2
     - Level 3
   * - ``http://`` / ``https://``
     - ONDAS servers
     - ONDAS or NWS TGFTP (auto-detected)
   * - ``s3://``
     - Custom S3 bucket (``s3://bucket-name/``)
     - Custom S3 bucket (``s3://bucket-name/``)

For HTTP/HTTPS Level 3 URLs, Supercell Wx probes the server for ONDAS
configuration files. If an ONDAS config is found, ONDAS listing and product
paths are used; otherwise, NWS TGFTP directory listing is assumed.

Environment variables
---------------------

The command line options set the following environment variables, which can also
be set directly:

* ``SCWX_LEVEL2_DATA_PROVIDER_URL`` — Level 2 provider base URL
* ``SCWX_LEVEL3_DATA_PROVIDER_URL`` — Level 3 provider base URL

When a provider URL contains ``iastate.edu``, ``allisonhouse.com``, or
``weatherpulse.com``, Supercell Wx also loads an extended radar site list
appropriate for that provider.

Examples
--------

Iowa State Mesonet (Level 2):

.. code-block:: none

   supercell-wx --level2-provider https://mesonet-nexrad.agron.iastate.edu/level2/raw/

NWS TGFTP (Level 3):

.. code-block:: none

   supercell-wx --level3-provider https://tgftp.nws.noaa.gov/SL.us008001/DF.of/DC.radar/

Custom S3 bucket (Level 2):

.. code-block:: none

   supercell-wx --level2-provider s3://unidata-nexrad-level2/

Both levels can be specified together:

.. code-block:: none

   supercell-wx --level2-provider https://mesonet-nexrad.agron.iastate.edu/level2/raw/ --level3-provider https://tgftp.nws.noaa.gov/SL.us008001/DF.of/DC.radar/

Windows shortcut example
------------------------

Add provider options to the **Target** field of a shortcut, after the executable
path:

.. code-block:: none

   "C:\Program Files\Supercell Wx\supercell-wx.exe" --level2-provider https://mesonet-nexrad.agron.iastate.edu/level2/raw/
