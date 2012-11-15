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

Original value looks like:

.. code-block:: php
    
    $stats = array(
        array(link_to('items', null, total_records('Item')), __('items')),
        array(link_to('collections', null, total_records('Collection')), __('collections')),
        array(link_to('tags', null, total_records('Tag')), __('tags'))
    ); 