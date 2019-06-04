###################
file_markup_options
###################

.. versionadded:: 2.7

*****
Usage
*****

Modify the options passed to :php:func:`file_markup`

Unlike the :doc:`file_markup` filter, this filter allows you to change
options that Omeka uses when rendering HTML for a file, meaning you can
alter the output without having to write completely new markup yourself.

*****
Value
*****

``array`` $options
    Array of options for ``file_markup``
    
*********
Arguments
*********

:php:class:`File` file
    The file object

********
Examples
********

Add ``target="_blank"`` to all links to original files:

.. code-block:: php

    class MyPlugin extends :php:class:`Omeka_Plugin_AbstractPlugin`
    {
        protected $_filters = array('file_markup_options');
        
        public filterHtmlPurifierConfigSetup($options, $args)
        {
            $options['linkAttributes']['target'] = '_blank';
            return $options;
        }    
    }

********
See Also
********

:php:func:`file_markup` documentation for a list of possible options
