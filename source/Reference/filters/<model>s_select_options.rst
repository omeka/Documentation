
#######################
<model>s_select_options
#######################


*****
Usage
*****

Filters the options for a select element for the <model>'s table. Useful if your plugin adds relations between the <model>'s table and another table.


.. note::

    Use the plural form of the <model>


*****
Value
*****

``array`` $options
    Array of key-value pairs, where the key is usually a record ID and the value is determined by the model's table 

*********
Arguments
*********

None

********
See Also
********

:ref:`fgettableoptions`
:ref:`flabeltableoptions`
:php:meth:`Omeka_Db_Table::findPairsForSelectForm`


