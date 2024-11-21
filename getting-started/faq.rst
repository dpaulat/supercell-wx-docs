Frequently Asked Questions
==========================

.. contents::
   :local:

Before getting started, please read the `User Guide
<https://supercell-wx.readthedocs.io/en/stable/>`_.

`Latest Announcements <https://discord.com/channels/1021112836316995715/1021114968143315024>`_

General
-------

What is Supercell Wx?
~~~~~~~~~~~~~~~~~~~~~
Supercell Wx is a free, open source application to visualize live and archive
NEXRAD Level 2 and Level 3 data, and severe weather alerts. It displays
continuously updating weather data on top of a responsive map, providing the
capability to monitor weather events using reflectivity, velocity, and other
products. Extended functionality, including weather reports and lightning data
can be added using placefiles.

What do all these products mean? How do I read weather radar? How can I use this to identify and track tornadoes?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Below are some links to get you started:

- `How To Read Weather Radar <https://youtu.be/AeX2lMUfddQ?si=_q6sO32CrR183DJ5>`_
- `Descriptions of NEXRAD products <https://www.ncei.noaa.gov/products/radar/next-generation-weather-radar>`_
- `Using and Understanding Doppler Radar <https://www.weather.gov/mkx/using-radar>`_
- Your local National Weather Service location may offer both online and in
  person training sometimes for free! Find your location `here <https://www.weather.gov/srh/nwsoffices>`_.
- `NWS Education <https://www.weather.gov/education/>`_

Installation and Setup
----------------------

How much does Supercell Wx cost?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Supercell Wx is free and Open Source. `Donations <https://github.com/sponsors/dpaulat>`_
are welcome!

Where can I get the latest version?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://github.com/dpaulat/supercell-wx/releases

Will my computer run Supercell Wx?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Minimum requirements:

- Windows 10 (1809 or later), Windows 11
- Linux/X11 with support for GCC 11 (e.g., Fedora 34+, Ubuntu 22.04+, EndeavourOS, openSUSE Tumbleweed)
- OpenGL 3.3

How do I install and set up Supercell Wx?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
https://supercell-wx.readthedocs.io/en/stable/getting-started/initial-setup.html 

Where can I join the discussion? Where do I report a bug?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- `Join Discord <https://discord.com/invite/vFMV76brwU>`_
- `Report a bug <https://discord.com/channels/1021112836316995715/1118923154543353947>`_

What is planned for Supercell Wx? I have a suggestion or feature request.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
- Roadmap: https://github.com/users/dpaulat/projects/2/views/2
- Feature Request: Please check the roadmap on GitHub first. If the feature is
  not already planned or suggested, you can make a request on
  `Discord <https://discord.com/channels/1021112836316995715/1118952182352453683>`_.

Help! My map is blank even after I added MapTiler.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
There may be a blank space before or after your API key. Remove any spaces and
restart the app.

How can I contribute?
~~~~~~~~~~~~~~~~~~~~~
Head to `Developer Setup <https://supercell-wx.readthedocs.io/en/stable/development/developer-setup.html>`_
and `Contributing <https://github.com/dpaulat/supercell-wx/blob/develop/CONTRIBUTING.md>`_
to configure the Supercell Wx development environment for your IDE. Currently
Visual Studio and Visual Studio Code are recommended, with other IDEs remaining
untested at this time.

Using Supercell Wx
------------------

How do I...
~~~~~~~~~~~
Before asking, please read the `User Guide <https://supercell-wx.readthedocs.io/en/stable/>`_.

How do I set my home point?
~~~~~~~~~~~~~~~~~~~~~~~~~~~
**File > Settings > General > Default Radar Site**

How do I show multiple product panels?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
**File > Settings > General > Grid Width** and **Grid Height**

For example, if you want a 4 pane view, set both the width and height to 2. To
choose the product for each pane, click anywhere in that pane and then select a
product from the Radar Toolbox navigation.

How do I enable Dark Mode?
~~~~~~~~~~~~~~~~~~~~~~~~~~
**File > Settings > General > Theme > Fusion**

How do I change the default time zone and format?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
**File > Settings > Default Clock Mode**

How do I see the specific values in a location?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Hold `SHIFT` and mouse over the location for the value related to the product you
have selected.

How can I change the colors of the radar products?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
**File > Settings > Palettes**

For a description of each product type, see https://www.ncei.noaa.gov/products/radar/next-generation-weather-radar.
The websites below have some of the most commonly used color palettes.

- https://grlevelxusers.com/grlevelx-goodies/categories/color-tables/
- https://grx.almanydesigns.com/downloads/ (Color Table Format V3.0+ is not supported)
- https://www.wxtools.org/reflectivity

What are placefiles and where can I find them?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Placefiles provide additional data not provided by NEXRAD that can be overlaid on top of the map. Some placefiles include things like METARs, air temperatures, real time lightning, storm spotter reports, SPC outlooks and Mesoscale information, etc.

- Supercell Placefiles: https://placefiles.supercellwx.net/
- Placefile Nation: https://placefilenation.com/

An updated list of placefiles is located in the documentation: https://supercell-wx.readthedocs.io/en/stable/user-guide/placefile-manager.html#placefile-resources.
