
################
Modifying Themes
################

****************************
Overriding default templates
****************************

Omeka has a set of default template files that all themes use, and override when
the desired page structure is different from the default.

The default theme files are in the folder ``/application/views/scripts`` in your Omeka installation.
Subfolders correspond to the pages that are seen along url patterns. For example, the page displayed at
``{YourOmekaSite}/items/show`` is produced by the file in ``/application/views/scripts/items/show.php``.

Themes might or might not override these files. The default theme, for example, has an ``items``
directory that overrides two of the default templates: ``random-featured.php`` and ``show.php`` ::

   items/
       random-featured.php
       show.php

If you want to modify a file in a theme, the first place to look is in the theme's own directories.
But notice that that will only work if the theme has overridden the default template. In many cases,
then, you will need to copy the default template files into the theme, taking care to maintain the 
directory structure.

So, for example, imagine wanting to modify the show page for items, the browse page for items, and
the show page for collections in the default theme.

The ``/items/show.php`` file is easy, since the default theme already includes it.

For the browse page for items, we need to copy ``/application/views/scripts/items/browse.php`` 
to ``/default/items/browse.php``

For the browse page for collections, we need to first create the directory: ``/default/collections``

Then we can copy ``/application/views/scripts/collections/browse.php`` 
to ``/default/collections/browse.php``

The result in the default theme will look like::
   
   items/
      random-featured.php
      browse.php
      show.php
   collections/
      browse.php

****************************
Adding custom configuration variables to a theme
****************************

For interface elements in a theme that you want site administrators to be able to edit from the Omeka UI (like homepage text, footer text, etc.), you may want to create new custom theme configuration variables. Theme configuration items are controlled by the  ``config.ini`` file in your theme's root directory. 

To add a new variable to your theme's configuration, you'll need to add lines like the following to the ``[config]`` section of your theme's ``config.ini`` file (at a minimum) ::

   my_custom_theme_variable.type = "text"
   my_custom_theme_variable.options.label = "Label for this variable which will be displayed on the theme config page"
   my_custom_theme_varaible.options.value = "Default value"
   my_custom_theme.variable.options.description = "Description for this variable which will be displayed on the theme config page"

The theme config interface uses the Zend Framework Form API on the back-end, and the ``type`` option defines which subclass of ``Zend\Form\Element\`` will be used to render this config item in the UI. So for example, you can use ``textarea``, ``text``, ``color``, ``checkbox``, etc. Each of these different element types will have their own config options. You may want to look through some of the different Omeka themes to see how these different elements are used (for example, Thanks Roy makes use of the ``color`` element).

The ``config.ini`` file also has a ``[groups]`` section which defines groupings by which the config is displayed in the user interface. To add a new element to an existing grouping, just add a new line of the form ::

   grouping.elements[] = "my_new_element"
   
To access theme variables in a theme file, you'll call ``get_theme_option`` using either the machine name of the variable from the ``config.ini`` file (e.g. ``get_theme_option('my_custom_theme_variable')``), or a human-readable version of the same, replacing underscores with spaces and capitalizing each letter (``get_theme_option('My Custom Theme Variable')``).
