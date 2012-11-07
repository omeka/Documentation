.. _migrating:

################################
Migrating your code to Omeka 2.0
################################

There are significant changes moving from Omeka 1.5 to Omeka 2.0. :ref:`principlesOfOmeka2` offers an overall guide to the principles, both for theme developers and plugin developers.

Here, you will find a skeleton of typical tasks that will be required to migrate your code. Consult the reference section for code details, and the notes about changes in our wiki will also be helpful.

*****************
Upgrading Plugins
*****************

As you look through the lists of typical tasks below, you might also want to consult :ref:`bestPracticesPlugins`

Typical tasks you will need to do to upgrade your plugins for Omeka 2.0 are:

* Change the classes your controllers and models extend from

    * Omeka_Controller_Action becomes :php:class:`Omeka_Controller_AbstractActionController` 

    * Omeka_Record becomes :php:class:`Omeka_Record_AbstractRecord`

* Update any helper functions you use in hooks for filters

* Change your hook callbacks to have an array passed in. Typically, the expected variable name passed in in version 1.5 (e.g. ``$user``) becomes the key for the corresponding data in the array, e.g. ``$user = $args['user'];`` See `Updating Plugins for 2.0: Hooks and Filters <http://omeka.org/codex/Updating_Plugins_For_2.0#Hooks_and_Filters>`_ 

* Update any filters you use. The third argument must now be an array to fit with the standard above.

* Change the helper functions used in the views ** All functions of the form ``loop_{record type}``, like ``loop_items()``, become ``loop("{record type}")``

* Change usage of function that previously echoed content. For example, ``<?php head(); ?>`` should now be ``<?php echo head(); ?>``.

Controllers
===========

* Update wrapper methods ``findById()``, ``getTable('TableName')``, ``getDb()`` 
   
   
Views
=====

Admin Views
-----------

* Many new CSS classes are available and should be used to ensure a consistent look and feel across Omeka plugins. It will be helpful to become familiar with them. For example, this is the new code structure to use if you need to create inputs yourself:
    
    .. code-block:: php
    
       <div class="field">
       <div id="administrator_email-label" class="two columns alpha"><label for="administrator_email" class="required">Administrator Email</label></div>
       <div class="inputs five columns omega"><input type="text" name="administrator_email" id="administrator_email" value="knguye27@gmu.edu <mailto:value=%22knguye27@gmu.edu>"></div>
       </div>

* Admin theme now displays an ``<h1>`` with the title you set for the page. You can remove those from your admin views
 
* Use new save panel features. For ease of use in the most common cases, the :php:class:`Omeka_Form_Admin` is available.


 
***************
Updating Themes
***************

The number of global functions has been cut nearly in half in Omeka 2.0. This will require many changes to your themes, but will also make the patterns of usage much easier to follow and much more consistent.

Here are a few of the basic tasks for upgrading.

* Change the various metadata-retrieval functions for different record types (e.g., ``item()``, ``collection()``, etc) to the generalized :ref:`fmetadata` function.

* Change the loop structure for the various record types (e.g., ``loop_items()``, ``loop_collections``, etc) to the generalized :ref:`loop` function. Note that the structure changes from
    
    .. code-block:: php
    
        while(loop_items()) :
    
    to
    
    .. code-block:: php
    
        foreach(loop('items') as $item):
        

* Change other global functions that have changed. There is `a complete list of old and new function names on our wiki <http://omeka.org/codex/Updating_Plugins_For_2.0#Function_Replacements>`_. 
 
* Update calls to hooks and filters (wherever you use :ref:`ffire_plugin_hook` and :ref:`fapply_filters`). Typically, the expected variable name passed in in version 1.5 (e.g. ``$user``) becomes the key for the corresponding data in the array, e.g. ``$user = $args['user'];`` See `Updating Plugins for 2.0: Hooks and Filters <http://omeka.org/codex/Updating_Plugins_For_2.0#Hooks_and_Filters>`_







