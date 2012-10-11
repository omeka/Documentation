.. principlesOfOmeka2.


#######################
Principles of Omeka 2.0
#######################

People who are familiar with conventions and patterns from Omeka 1.x will see many changes. Here are some ofbroad principles that went into the changes to Omeka 2.0


**************
Record-centric
**************

The design of Omeka 1.x tended to treat different database records as superficially very different, despite the fact they all inherit from the same class. Thus, we had functions ``item()`` alongside ``collection()``, both of which performed very similar jobs of retrieving data from a record. Similarly, we had ``loop_items()`` and ``loop_collections()``. That pattern extended into our plugins, e.g. ``simple_page()`` and ``loop_simple_pages()``. This created excessive duplication of functionality.

In Omeka 2.0, we instead concentrated on the similarity across all records, designing single functions for similar tasks that work by either passing in a record or by passing in the name of the record type current in a view. For example, to retrieve the id from the current item in a view, use ``metadata('item', 'id')``. For a collection: ``metadata('collection', 'id')``.

This requires some attention to the names of your models and how they are assigned to the view. The first parameter to ``metadata()`` will be made singular, with the assumption that the view object has a record assigned to that property name. Similarly, looping assumes a plural form, an sets the current record to the singular name.


***************************
Function Naming Conventions
***************************

To make our function names more consistent and easier to understand, we have introduced the following naming conventions. 

* Functions that return an array or object begin with ``get_``
* Functions that return a boolean being with ``is_`` or ``has_``
* Functions do not echo a string. Instead they return the string


*********************************
Zend 2.0 Class Naming Conventions
*********************************

In anticipation of an eventual move to using Zend 2.0, we have reorganized our directories and class names to conform with Zend 2.0 conventions. Thus, the classes representing records and the table for them are no longer in the same directory. Instead, there is a ``Table`` directory inside the directory containing the models. The name of the table class should be the model's class name prefixed with ``Table_``, e.g. ``Table_SimplePagesPage``. 

