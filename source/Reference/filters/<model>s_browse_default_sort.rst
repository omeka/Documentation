############################
<model>s_browse_default_sort
############################

*****
Usage
*****

Filters the sort parameters of <model> records returned in default browse queries. If a sort param is passed in the query, this will not apply.

.. note::

    Use the plural form of the <model>

*****
Value
*****

``array`` $sortArray
   Array of parameters, with the first element being the sort_field parameter, and the second (optionally) the sort_dir.
   
*********
Arguments
*********

``array`` params
    All params passed to the search query