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

* Change the helper functions used in the views
** All functions of the form ``loop_{record type}``, like ``loop_items()``, become ``loop("{record type}")``
