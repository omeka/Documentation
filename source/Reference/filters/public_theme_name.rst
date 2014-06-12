#################
public_theme_name
#################


Filters the currently-selected public theme. Changing the theme name through this filter will cause Omeka to use a different theme to display the public interface. 

*****
Value
*****

``string`` $theme_name
    The name of the theme being used


*********
Arguments
*********

None


********
Examples
********

Force Omeka to use a different public theme

.. code-block:: php

    public function filterPublicThemeName($theme_name)
    {
        return 'my-custom-admin-theme';
    }
