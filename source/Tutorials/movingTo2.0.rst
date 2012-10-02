.. _migrating.

################################
Migrating your code to Omeka 2.0
################################



Principles of Omeka 2.0
=======================


Upgrading Plugins
-----------------

The basic tasks you will need to do to upgrade your plugins for Omeka 2.0 are:

* Change the classes your controllers and models extend from
** Omeka_Controller_Action becomes :ref:`Omeka_Controller_AbstractActionController`
** Omeka_Record becomes Omeka_Record_AbstractRecord

* Update any helper functions you use in hooks for filters

* Change your hook and filter callbacks to have an array passed in. 
Typically, the expected variable name passed in in version 1.5 (e.g. ``$user``) becomes the key for the corresponding data in the
array, e.g. ``$user = $args['user'];`` See `Updating Plugins for 2.0: Hooks and Filters <http://omeka.org/codex/Updating_Plugins_For_2.0#Hooks_and_Filters>`_ 
   .. note::
   ``admin_navigation_main`` still receives an array of the tabs -- not an array with a key called 'tabs'

* Update any filters you define. The third argument must now be an array to fit with the standard above
   
    
* Change the helper functions used in the views
** All functions of the form ``loop_{record type}``, like ``loop_items()``, become ``loop("{record type}")``

* Change usage of function that previously echoed content. For example, ``<?php head(); ?>`` should now be ``<?php echo head(); ?>``.

Controllers
```````````
* Update wrapper methods ``findById()``, ``getTable('TableName')``, ``getDb()`` 
   .. note::
   This means that you cannot use ``getTable()`` without an argument, as you previously could in a controller

   
   
   
Views
`````

Admin Views
+++++++++++

* Admin theme now displays an ``<h1>`` with the title you set for the page. You can remove those from your admin views

* replace form functions   

Edit/Add Views
--------------

* Use new panel

Browse Views
------------
   