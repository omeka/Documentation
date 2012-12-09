.. _modelbrowsesql:

##################
<model>_browse_sql
##################

*****
Usage
*****

Alters the :php:class:`Omeka_Db_Select` object when finding records of type <model> using the :php:meth:`Omeke_Db_Table::findBy` method.

``<model>`` should be the plural name of the model, e.g. ``items_browse_sql``

*********
Arguments
*********

:php:class:`Omeka_Db_Select` select
    The select object
    
``array`` params
    The parameters being used to build the select object    


********
Examples
********


