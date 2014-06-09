----------------------------
Omeka_View_Helper_Shortcodes
----------------------------

.. php:class:: Omeka_View_Helper_Shortcodes

    Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

    View helper for processing shortcodes in text.

    .. php:attr:: shortcodeCallbacks
    
        List of predefined shortcodes.

    .. php:method:: addShortcode(string $shortcodeName, callback $callback)
    
        Add a new shortcode.
        
        :param string $shortcodeName: Name of the shortcode
        :param callback $callback: Callback function that will return the shortcode content

    .. php:method:: shortcodes(string $content)
    
        Process any shortcodes in the given text.
        
        :param string $content: 
        :returns: string

    .. php:method:: handleShortcode(array $matches)
    
        Parse a detected shortcode and replace it with its actual content.
        
        :param array $matches: 
        :returns: string

    .. php:method:: parseShortcodeAttributes(string $text)
    
        Parse attributes section of a shortcode.
        
        :param string $text: 
        :returns: array

    .. php:method:: shortcodeRecentItems(array $args, Omeka_View $view)
    
        Shortcode for printing recently added items.
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeFeaturedItems(array $args, Omeka_View $view)
    
        Shortcode for printing featured items.
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeItems(array $args, Omeka_View $view)
    
        Shortcode for printing one or more items
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeCollections(array $args, Omeka_View $view)
    
        Shortcode for printing one or more collections
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeRecentCollections(array $args, Omeka_View $view)
    
        Shortcode for printing recent collections
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeFeaturedCollections(array $args, Omeka_View $view)
    
        Shortcode for printing featured collections
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string

    .. php:method:: shortcodeFile(array $args, Omeka_View $view)
    
        Shortcode for displaying a single file.
        
        :param array $args: 
        :param Omeka_View $view: 
        :returns: string