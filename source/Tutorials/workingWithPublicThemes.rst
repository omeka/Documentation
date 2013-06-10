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