
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

