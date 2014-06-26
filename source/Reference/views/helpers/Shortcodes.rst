----------------------------
Omeka_View_Helper_Shortcodes
----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_Shortcodes

extends :php:class:`Zend_View_Helper_Abstract`

    View helper for processing shortcodes in text.

    .. php:attr:: shortcodeCallbacks

        protected array

        List of predefined shortcodes.

    .. php:method:: addShortcode($shortcodeName, $callback)

        Add a new shortcode.

        :type $shortcodeName: string
        :param $shortcodeName: Name of the shortcode
        :type $callback: callback
        :param $callback: Callback function that will return the shortcode content

    .. php:method:: shortcodes($content)

        Process any shortcodes in the given text.

        :type $content: string
        :param $content:
        :returns: string

    .. php:method:: handleShortcode($matches)

        Parse a detected shortcode and replace it with its actual content.

        :type $matches: array
        :param $matches:
        :returns: string

    .. php:method:: parseShortcodeAttributes($text)

        Parse attributes section of a shortcode.

        :type $text: string
        :param $text:
        :returns: array

    .. php:method:: shortcodeRecentItems($args, $view)

        Shortcode for printing recently added items.

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeFeaturedItems($args, $view)

        Shortcode for printing featured items.

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeItems($args, $view)

        Shortcode for printing one or more items

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeCollections($args, $view)

        Shortcode for printing one or more collections

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeRecentCollections($args, $view)

        Shortcode for printing recent collections

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeFeaturedCollections($args, $view)

        Shortcode for printing featured collections

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string

    .. php:method:: shortcodeFile($args, $view)

        Shortcode for displaying a single file.

        :type $args: array
        :param $args:
        :type $view: Omeka_View
        :param $view:
        :returns: string
