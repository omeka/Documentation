################
display_option_*
################

*****
Usage
*****

This family of filters is used whenever the :php:func:`option` theme function is called, 
to filter the value returned from the database before it is displayed.

The name of the particular filter that should be used is made by appending the name of the 
option to "display_option_". 

*********
Arguments
*********

``string`` $option

    The original value of the option.

********
Examples
********

To print the site title, a theme writer would do the following: 

.. code-block:: php

    <?php echo option('site_title'); ?>


If you want to prepend "Omeka: " to the title of every printed page:

.. code-block:: php

    public function filterDisplayOptionSiteTitle($option)
    {
        return "Omeka: $option";
    }
