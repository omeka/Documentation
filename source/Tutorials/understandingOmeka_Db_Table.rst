.. _understandingomekadbtable:

############################
Understanding Omeka_Db_Table
############################

******
Basics
******

Omeka_Db_Table is part of the Model part of Model-View-Controller in Omeka. It provides
the methods for querying the database and returning results as :php:class:`Omeka_Record_AbstractRecord`
objects. The most frequently used methods in this class are :php:meth:`Omeka_Db_Table::findBy` and 
:php:meth:`Omeka_Db_Table::find`

:php:meth:`Omeka_Db_Table::find` simply returns a single record by the ``id`` passed in.

:php:meth:`Omeka_Db_Table::findBy` returns an array of records that match the criteria passed in 
with the ``$param`` argument. When creating your subclasses of :php:class:`Omeka_Db_Table`, you will
want to understand first how to build filters for queries using :php:meth:`Omeka_Db_Table::findBy`.

:php:meth:`Omeka_Db_Table::findBy` works by manipulating a :php:class:`Omeka_Db_Select` object, which 
simplifies the process fo building simple SQL queries. 

*****************
Filtering Queries
*****************

:php:meth:`Omeka_Db_Table::findBy` calls method :php:meth:`Omeka_Db_Table::applySearchFilters`. It 
takes a ``$select`` argument, and a ``$params`` argument.  By default, this method simply checks 
the ``$params`` array passed in, looking for keys that match column names. For each match, 
a ``WHERE`` clause is generated.

Sometimes, though, it makes sense to add more complex logic. For example, you might want to filter
a query by conditions on joining another table, or you might need to call a method in your subclass
to process the data passed in the value of the parameter key. In such cases, Omeka has moved toward a
pattern of using ``filterBy*`` methods.  

In this pattern, you build more complex logic for adding a ``WHERE`` clause by passing in the ``$select``
object, and the value that you want to work with. :php:class:`Table_Collection` offers a good example.

   .. code-block:: php
   
       public function filterByPublic($select, $isPublic)
       {         
           $isPublic = (bool) $isPublic; // this makes sure that empty strings and unset parameters are false
   
           //Force a preview of the public collections
           if ($isPublic) {
               $select->where('collections.public = 1');
           } else {
               $select->where('collections.public = 0');
           }
       }

This method does a little double-checking on the value passed in for whether the collection has
been marked public, then applies the appropriate ``WHERE`` clause to the ``$select`` object.

In :php:meth:`Table_Collection::applySearchFilters`, we see the following to call it:

   .. code-block:: php
   
        if(array_key_exists('public', $params)) {
            $this->filterByPublic($select, $params['public']);
        }
     
     
   
