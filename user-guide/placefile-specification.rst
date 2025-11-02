========================
Place File Specification
========================

Overview
========

The Supercell Wx Place File Specification is adapted from the GRLevelX Place File Specification found at https://grlevelx.com/manuals/gis/files_places.htm, with extensions added for Supercell Wx (statements prefixed with ``scwx-``).

Place files are user-supplied text files containing drawing statements. They can be on a local file system or given as a URL. When a URL is requested, the latitude and longitude of the radar site being viewed are included as parameters (e.g. ``?lat=nnn.nnn&lon=nnn.nnn``) along with the placefile version supported (e.g. ``&version=1.5``) and DPI of the display (e.g., ``&dpi=96``).

Supercell Wx will always send a User Agent of ``SupercellWx/<version>``, so you can detect when to enable support for custom Supercell Wx extensions to your Place File generator.

----

File Settings
=============

Title
-----

.. code-block:: none

   Title: title

:title: Sets the title of the Place File.

Threshold
---------

.. code-block:: none

   Threshold: nautical_miles

:nautical_miles: Sets the view threshold in miles for subsequent Place statements. The default threshold is 999.

HSLuv
-----

.. code-block:: none

   HSLuv: value

:value: Enables or HSLuv with ``true``, or disables with ``false``. The default is disabled.

Color
-----

.. code-block:: none

   Color: red green blue [alpha]
   Color: hue saturation lightness

Sets the default color of subsequent Place statements. The default color is white (255 255 255).

:red: Red color component (0-255)
:green: Green color component (0-255)
:blue: Blue color component (0-255)
:alpha: *(optional)* Alpha color component (0-255)

When in HSLuv mode, instead of RGBA, HSL components are used instead.

:hue: Hue component
:saturation: Saturation component
:lightness: Lightness component

.. note:: When in HSLuv mode, the alpha channel is not configurable.

TimeRange
---------

.. code-block:: none

   TimeRange: start_time end_time

*Since Place File version 1.5*

Sets the time range of subsequent Place statements. Time is specified in the format ``YYYY-MM-DDThh:mm:ss``.

:start_time: The time to begin displaying the Place statement, inclusive
:end_time: The time to end displaying the Place statement, exclusive

Refresh
-------

.. code-block:: none

   Refresh: minutes

:minutes: Specifies the amount of time in minutes until the placefile is reloaded.

RefreshSeconds
--------------

.. code-block:: none

   RefreshSeconds: seconds

:seconds: Specifies the amount of time in seconds until the placefile is reloaded.

----

Icon Statements
===============

IconFile
--------

.. code-block:: none

   IconFile: fileNumber, iconWidth, iconHeight, hotX, hotY, fileName

:fileNumber: A number from 1 to 8 used to reference the file in subsequent Icon statements. The number cannot be used in other IconFile statements.
:iconWidth: Width of each icon in the file (pixels)
:iconHeight: Height of each icon in the file (pixels)
:hotX: Zero-based horizontal center of the icon, used for placement and as the center of rotation. Must be less than iconWidth.
:hotY: Zero-based vertical center of the icon, used for placement and as the center of rotation. Must be less than iconHeight.
:fileName: Local, network, or URL filename (PNG, JPG, TIF supported). If no alpha channel is in the file, solid black (0,0,0) is made transparent.

Icon
----

.. code-block:: none

   Icon: lat, lon, angle, fileNumber, iconNumber, hoverText

:lat: Latitude coordinate where the icon hotspot is placed
:lon: Longitude coordinate where the icon hotspot is placed
:angle: Clockwise angle of rotation of the icon (degrees)
:fileNumber: File number from earlier IconFile statement
:iconNumber: Number of the icon to draw from 1 to the number of icons in the icon file. Icons in an icon file are assigned by row from left to right, top to bottom.
:hoverText: *(optional)* Text displayed when the mouse cursor hovers over the lat, lon of the icon

scwx-ModulateIcon
-----------------

.. code-block:: none

   scwx-ModulateIcon: red green blue [alpha]
   scwx-ModulateIcon: hue saturation lightness

Sets the modulate color of subsequent Icon statements. The default modulate color is white (255 255 255 255).

:red: Red color component (0-255)
:green: Green color component (0-255)
:blue: Blue color component (0-255)
:alpha: *(optional)* Alpha color component (0-255)

When in HSLuv mode, instead of RGBA, HSL components are used instead.

:hue: Hue component
:saturation: Saturation component
:lightness: Lightness component

----

Text Statements
===============

Font
----

.. code-block:: none

   Font: fontNumber, pixels, flags, "face"

:fontNumber: Number to assign to the font, from 1 to 8. Font numbers cannot be used in any other Font statement.
:pixels: Pixel height of the font
:flags: Font attribute flags: 1 means bold, 2 means italic
:face: Face name of the font to use

Place
-----

.. code-block:: none

   Place: lat, lon, string

:lat: Latitude coordinate for the center of the text string
:lon: Longitude coordinate for the center of the text string
:string: Text to display

The Place statement gives the location and string to display. Commas separate each field. The string can contain spaces and is trimmed of leading and trailing spaces before display.

Text
----

.. code-block:: none

   Text: lat, lon, fontNumber, "string", "hover"

:lat: Latitude coordinate for the center of the text string
:lon: Longitude coordinate for the center of the text string
:fontNumber: Font number from earlier Font statement
:string: Text to display
:hoverText: *(optional)* Text displayed when the mouse cursor hovers over the lat, lon of the string

----

Composite Objects
=================

Object
------

.. code-block:: none

   Object: lat, lon
       ...
   End:

:lat: Latitude of composite object center location
:lon: Longitude of composite object center location

An Object statement must be paired with an End statement. All other statements can appear in between the pair. When inside an Object block, the lat, lon values are interpreted as x, y offsets in pixels from the center of the object. Positive offsets are to the right and towards the top of the screen.

----

Drawing Statements
==================

Line
----

.. code-block:: none

   Line: width, flags [, hover_text]
       lat, lon
       ...
   End:

:width: Width of line in pixels
:flags: Currently unused
:hover_text: *(optional)* Text to display when user hovers mouse cursor over the line
:lat: Latitude coordinate of point on line
:lon: Longitude coordinate of point on line

The Line statement draws a line along the list of lat,lon points. There can be up to 10,000 points in each line. The color of the line is set by a previous Color statement.

Triangles
---------

.. code-block:: none

   Triangles:
       lat, lon [, r, g, b [, a]]
       lat, lon [, h, s, l]
       ...
   End:

:lat: Latitude coordinate of a vertex of a triangle
:lon: Longitude coordinate of a vertex of a triangle
:r: *(optional)* Red color component for the vertex (0-255)
:g: *(optional)* Green color component for the vertex (0-255)
:b: *(optional)* Blue color component for the vertex (0-255)
:a: *(optional)* Alpha (transparency) component for the vertex (0-255)

The Triangles statement draws triangles from groups of three color vertices. Vertex colors are smoothly interpolated across the triangle faces.

When in HSLuv mode, instead of RGBA, HSL components are used instead.

:hue: Hue component
:saturation: Saturation component
:lightness: Lightness component

Image
-----

.. code-block:: none

   Image: image_file
       lat, lon, Tu [, Tv]
       ...
   End:

:image_file: Image file for texture (PNG, JPG, TGA supported)
:lat: Latitude coordinate of a vertex of a triangle
:lon: Longitude coordinate of a vertex of a triangle
:Tu: Horizontal texture coordinate for the vertex, where 0.0 is the left edge of the image and 1.0 is the right edge
:Tv: *(optional)* Vertical texture coordinate for the vertex, where 0.0 is the top edge of the image and 1.0 is the bottom edge

The Image statement draws triangles from groups of three textured vertices. Each vertex has texture coordinates that specify where in the image_file to retrieve the color. The system smoothly interpolates Tu, Tv across the triangle faces.

scwx-ImageXY
------------

.. code-block:: none

   scwx-ImageXY: image_file
       x, y, ax, ay, Tu [, Tv]
       ...
   End:

:image_file: Image file for texture (PNG, JPG, TGA supported)
:x: Zero-based horizontal coordinate of the image
:y: Zero-based vertical coordinate of the image
:ax: Horizontal anchor point for the image in NDC coordinates. -1.0 is the left of the viewport, and 1.0 is the right of the viewport.
:ay: Vertical anchor point for the image in NDC coordinates. -1.0 is the bottom of the viewport, and 1.0 is the top of the viewport.
:Tu: Horizontal texture coordinate for the vertex, where 0.0 is the left edge of the image and 1.0 is the right edge
:Tv: *(optional)* Vertical texture coordinate for the vertex, where 0.0 is the top edge of the image and 1.0 is the bottom edge

Polygon
-------

.. code-block:: none

   Polygon:
       lat1, lon1 [, r, g, b [, a]]    ; start of the first contour
       ...
       lat1, lon1                       ; repeating the first point closes the contour

       lat2, lon2                       ; next point starts a new contour
       ...
       lat2, lon2                       ; and repeating it ends the contour
   End:

:lat: Latitude coordinate of a vertex
:lon: Longitude coordinate of a vertex
:r: *(optional)* Red color component for the vertex (0-255)
:g: *(optional)* Green color component for the vertex (0-255)
:b: *(optional)* Blue color component for the vertex (0-255)
:a: *(optional)* Alpha (transparency) component for the vertex (0-255)

The Polygon statement specifies outer and inner lines that make the boundary of a filled shape. The polygon is filled in ODD winding mode. Each point on the contour can have its own RGBA color and the colors are smoothly interpolated across the polygon interior.

.. note::
   More information on contours and winding modes can be found in standard computer graphics references.
