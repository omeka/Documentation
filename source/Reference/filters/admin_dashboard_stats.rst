.. _admindashboardstats:

#####################
admin_dashboard_stats
#####################


*****
Usage
*****

Add content to the stats row at the top of the dashboard


*****
Value
*****

``array`` $stats
    Array of links for the stats row
    
*********
Arguments
*********

:php:class:`Omeka_View` view
    The current view object
    
    
********
Examples
********

The structure of the items in the ``$stats`` array changed in Omeka 3.1. In 3.1 and up,
each array entry should follow this pattern:

.. code-block:: php

    $stats['items'] = array(total_records('Item'), __('items'));

The array key is a record type that is passed to :php:func:`link_to`, and the value array's
two items are first the number to display, and second the label.

For versions prior to 3.1, the structure is as follows:

.. code-block:: php
    
    $stats = array(
        array(link_to('items', null, total_records('Item')), __('items')),
        array(link_to('collections', null, total_records('Collection')), __('collections')),
        array(link_to('tags', null, total_records('Tag')), __('tags'))
    ); 
