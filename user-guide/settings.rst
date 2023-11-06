Settings
=============

Settings can be accessed from the menu by selecting **File > Settings**. The settings menu
contains two categories, General and Palettes. 

.. image:: images/settings-general-04-restore-defaults.png

Settings can be globally restored to default
with the Restore Defaults button in the lower left corner.

.. image:: images/settings-general-05-individual-restore-default.png

Individual settings can be restored to their default with the circle arrow button
beside the respective setting.

.. note:: Most settings will require reloading the application to take effect.

General
----------

Default Radar Site
^^^^^^^^^^^^^^^^^^
Choose which radar site will load automatically upon opening the app. The map will also
be centered over the selected radar site.

Grid Width and Height
^^^^^^^^^^^^^^^^^^^^^
These settings allow multiple radar products to be viewed simultaneously. Changing 
Grid Width will create panes side by side, while Grid Height will create panes top and 
bottom. The maximum value for both is two.

*Layout with a Grid Width of 2 and a Grid Height of 1*

.. image:: images/settings-general-01-gridwh-w2-h1-small.png

*Layout with a Grid Width of 1 and a Grid Height of 2*

.. image:: images/settings-general-02-gridwh-w1-h2-small.png

*Layout with a Grid Width of 2 and a Grid Height of 2*

.. image:: images/settings-general-03-gridwh-w2-h2-small.png

Map Provider
^^^^^^^^^^^^
Select the provider for the map underlays. Currently Mapbox and MapTiler are
supported. 

.. note:: The map types available on the Map Style dropdown in the Radar Toolbox
    will depend on the selected map provider. 

Mapbox API Key
^^^^^^^^^^^^^^
Input API key to be used when using Mapbox as the map provider

MapTiler API Key
^^^^^^^^^^^^^^^^
Input API key to be used when using MapTiler as the map provider. The available API keys can be
found `on the account API Keys page
<https://cloud.maptiler.com/account/keys/>`_

Default Alert Action
^^^^^^^^^^^^^^^^^^^^
Changes what happens when selecting an alert in the Alerts panel.

- Go (Default) - Switch to issuing radar site and pan map to location. 
- View - Open Alert to view text issued from NWS.

Update Notifications Enabled
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Notify the user of updates to Supercell Wx.

Debug Enabled
^^^^^^^^^^^^^
Enables the debug options menu.

Palettes
----------

The map and radar display have multiple customization options, including color
tables. The default color tables come from `NOAA's Weather and Climate Toolkit
<https://www.ncdc.noaa.gov/wct/index.php>`_, but can be modified from the
**Palettes** category in the **Settings** dialog. Color tables are compatible
with the `GRLevelX <http://www.grlevelx.com/>`_ `Color Table File Specification
<http://www.grlevelx.com/manuals/color_tables/files_color_table.htm>`_.

.. image:: images/settings-palette-01-color-tables.png

Additional color tables can be found at a number of sites, including:

- https://grlevelxusers.com/grlevelx-goodies/categories/color-tables/
- https://www.wxtools.org/

In addition to color tables, alert colors can also be modified. Use the text box
to specify a color in ARGB hexadecimal format (#aarrggbb), or use the color
picker to select a color.

.. image:: images/settings-palette-02-alerts.png

Text
----------

Under the text menu, the user is given several different customization options to adjust the font and style to the user's liking.

.. image:: images/settings-text-01.png

Choosing your font
^^^^^^^^^^^^^^^^^^

The user can select the font they'd like to use by choosing either the default display item or the tooltip display item, and then hitting the 3 dots next to the font name.

.. image:: images/settings-text-02-select-font.png

*Choose the font, font style, font size, effects and writing system*

.. image:: images/settings-text-03-select-font.png

Tooltip method
^^^^^^^^^^^^^^

The tooltip method allows the user to change the method used for which pop-ups are displayed. The user is also able to change the character wrap size if the text from placefiles appear to be too long on the user's screen.

*Tooltip methods*

.. image:: images/settings-text-04-tooltip-method.png

*Character wrap and placefile text drop shadow*

.. image:: images/settings-text-05-character-wrap.png
