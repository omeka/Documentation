##########
public_nav
##########

.. php:function:: public_nav(array $navArray, string|null $navType, integer|null $maxDepth = 0)

    Helper function to be used in public themes to allow plugins to modify the 
    navigation of those themes.
    
    Plugins can modify navigation by adding filters to specific subsets of the navigation. For instance, most themes
    will have what might be called a 'main'
    navigation set on the header of the site. This main navigation header would be attached to a filter called
    'public_navigation_main', which would always act on that particular navigation. You would signal to the plugins to
    differentiate between the different navigation elements by passing the 2nd argument as 'main', so that it knew that
    this was the main navigation.
    
    :param array $navArray: 
    :param string|null $navType: 
    :param integer|null $maxDepth: 
    :returns: string HTML

*****
Usage
*****



********
Examples
********



