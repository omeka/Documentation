.. workingwithpublicthemes:

############################
Working with Public Themes
############################

Themes included in Omeka 2.0, "Thanks, Roy" and "Seasons", have been rebuilt with two new features: Compass project files and Susy responsive grids. `Compass <http://www.compass-style.org>`_ is a CSS framework that utilizes the `Sass <http://www.sass-lang.com/>`_ preprocessor to generate styles, making it easier for front-end developers to manage typography, margin units, colors, and more. `Susy <http://susy.oddbird.net>`_ is a responsive grid library that can be imported into Compass. Responsive grids allow sites to adapt to the browser width, making content more easily readable on a variety of devices.

For users who want to start using Compass and Susy with Omeka themes, here are recommended tutorials for installation. Both Compass and Susy require Ruby to be installed, and users should be comfortable with the command line.

* `The Sass Way: Getting started with Sass and Compass <http://thesassway.com/beginner/getting-started-with-sass-and-compass>`_
* `The official Compass installation tutorial <http://compass-style.org/install/>`_
* `The official Susy installation tutorial <http://susy.oddbird.net/guides/getting-started/>`_

Those who simply want to edit the CSS without getting into preprocessors can ignore the 'css/sass' folder completely and focus on .css files. **Note:** if you edit a .css file but later decide to use Sass, you should back up and make note of your changes before compiling for the first time. Changes made in .scss files overwrite any changes made to .css files.

########################
Omeka Theme Style Guide
########################

=====
Intro
=====
This style guide is for use in writing themes for Omeka 2.0+. It borrows heavily from the `Github style guide <https://github.com/styleguide/css>`_. This style guide is a work in progress, so excuse our dust.

=============
Configuration
=============
When setting up the Compass configuration for a theme, the settings should be as follows::

      http_path = "/"
      css_dir = "/"
      sass_dir = "sass"
      images_dir = "images"
      javascripts_dir = "javascripts"
      output_style = :expanded
      line_comments = false

When using Git, make sure you include a ``.gitignore`` in the root of your theme folder. The most common inclusions are::

      .DS_Store
      .sass-cache/

============
Organization
============

As such, the `/css` directory of an Omeka theme should follow the following structure::

      |- css
      |--- sass
      |    |--- _base.scss
      |    |--- _normalize.scss
      |    |--- _print.scss
      |    |--- _screen.scss
      |    |--- style.scss
      |--- config.rb
      |--- style.css


Group your styles using commented headings and include a table of contents. Here is an example of a table of contents::

      /*
      Table of Contents
      =================
      -- General HTML Elements
      ----- Headings
      ----- Form Elements
      -- Global Classes
      -- Navigation
      ----- Pagination
      -- Header 
      -- Footer
      -- Content
      */

An example of a section heading::

      /* !---------- Header ---------- */

Use the ``/*`` style of comments for headings you want to appear in the ``.css`` file. For Sass-only sections, such as the variables set in ``_bass.scss``, use the ``//`` commenting syntax. The ``!`` at the beginning of the header helps bookmark sections for theme writers using the Coda web editor.

----------
_base.scss
----------

The ``_base.scss`` file should include any variables used across multiple ``.scss`` files. Otherwise, the variables appear at the top of the file in which they are used.

---------------
_normalize.scss
---------------
We like to use Nicolas Gallagher's `normalize.css <http://necolas.github.io/normalize.css/>`_ as our reset stylesheet. Include it as a ``.scss`` file and import it into ``_base.scss``.

------------
_screen.scss
------------
If you are creating a responsive theme, ``_screen.scss`` is the default file for mobile-first styles. Separate ``.scss`` files should be used to group styles for different resolutions. Files should be named based on the breakpoint, i.e. ``_screen_480px.scss``, ``_screen_360px.scss``, ``_screen_40em.scss``.

----------
style.scss
----------
If you are not creating a responsive theme, all styles should go in ``style.scss``. The ``style.scss`` file should also import ``_base.scss`` and ``_normalize.scss``. Responsive themes should also import all ``_screen_x.scss`` files here.

==============
General styles
==============

* Use 4 spaces for indentation. Do not use tabs.
* Use spaces after ``:`` when writing property declarations.
* Put spaces before ``{`` in rule declarations.
* Use hex color codes ``#000`` unless using rgba.

