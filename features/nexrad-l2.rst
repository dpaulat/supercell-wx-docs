NEXRAD Level 2
==============

Supercell Wx loads NEXRAD Level 2 data from AWS S3 by default. Level 2 products
include base reflectivity, velocity, and dual-polarization fields at full radar
resolution.

Alternate Level 2 data sources, including ONDAS HTTP servers and custom S3
buckets, can be selected with the ``--level2-provider`` command line option or
the ``SCWX_LEVEL2_DATA_PROVIDER_URL`` environment variable. See
:doc:`../user-guide/command-line-options` for supported URL formats and examples.
