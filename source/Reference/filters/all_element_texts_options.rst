.. _allelementtextsoptions:

#########################
all_element_texts_options
#########################

.. versionadded:: 3.2

*****
Usage
*****

Filters the options passed to :php:func:`all_element_texts`.

*****
Value
*****

``array`` $options
    Array of the options passed to a call to all_element_texts.

*********
Arguments
*********

:php:class:`Omeka_Record_AbstractRecord` record
    The record all_element_texts is being called on.
    
********
Examples
********

Change the partial used to display elements

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = ['all_element_texts_options'];
    
        public filterActionContexts($options, $args)
        {
            $options['partial'] = 'common/custom-record-metadata.php';
            return $options;
        }
    }
