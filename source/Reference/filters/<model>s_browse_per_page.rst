########################
<model>s_browse_per_page
########################

*****
Usage
*****

Filters the number of <model> records returned in browse queries.

.. note::

    Use the plural form of the <model>

*****
Value
*****

``int`` $perPage
   The number of records to return
   
*********
Arguments
*********

:php:class:`Omeka_Controller_AbstractActionController` controller
    The controller issuing the query