################
admin_theme_name
################

*****
Usage
*****

Filters the currently-selected admin theme. Changing the theme name through this filter will cause Omeka to use a different theme to display the admin interface. 

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

Force Omeka to use a different admin theme

.. code-block:: php

    public function filterAdminThemeName($theme_name)
    {
        return 'my-custom-admin-theme';
    }
