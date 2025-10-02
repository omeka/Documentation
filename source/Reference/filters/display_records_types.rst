.. _displayrecordstypes:

#####################
display_records_types
#####################

.. versionadded:: 3.2

*****
Usage
*****

Filters record types available to :php:func:`display_records` and :php:func:`get_display_records`.

*****
Value
*****

``array`` $recordTypes
    Array of supported record types. The keys are record type names (``Item``, ``Collection``, etc.)
    and the values are arrays with two values: ``partial`` is the default partial to use to display
    one record of this type (often a ``single.php`` partial view), and ``alias`` is the name of a
    variable that will be set on the partial and assigned the record object being displayed (this
    is in addition to ``record``, which is always set on the partial; ``alias`` is typically useful
    when using existing partials which aren't written to expect a ``record`` variable).

*********
Arguments
*********

This filter takes no additional arguments.
    
********
Examples
********

Support a plugin-added record type in ``display_records`` and ``get_display_records``.
This sets a default partial used to display each record. When displaying the records, 
that partial will be called and recieve variables ``record`` and ``myRecord``, both set to
the currently-displaying record object.

.. code-block:: php

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_filters = ['display_records_types'];
    
        public filterDisplayRecordsTypes($recordTypes, $args)
        {
            $recordTypes['MyPlugin_MyRecord'] = ['partial' => 'my-plugin/my-record/single.php', 'alias' => 'myRecord'];
            return $recordTypes;
        }
    }
