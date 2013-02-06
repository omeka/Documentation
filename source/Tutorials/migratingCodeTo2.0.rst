.. _migrating:

################################
Migrating your code to Omeka 2.0
################################

There are significant changes moving from Omeka 1.5 to Omeka 2.0. :ref:`principlesOfOmeka2` offers an overall
guide to the principles, both for theme developers and plugin developers.

Here, you will find a skeleton of typical tasks that will be required to migrate your code. Consult the
:doc:`reference section </Reference/index>` for code details.

*****************
Omeka an Archive?
*****************

While archivists can (and many do) use Omeka as a presentation layer to their 
digital holdings, Omeka is not archival management software. To underscore this 
fact, we've removed all mention of the word "archive" in the Omeka codebase and 
filesystem. This will require at least two additional steps when upgrading from 
earlier versions to 2.0:

1. Rename the archive/files/ directory to /archive/original/:

   .. code-block:: sh
   
      $ mv /path/to/omeka/archive/files/ /path/to/omeka/archive/original/

2. Rename the archive/ directory to files/:

   .. code-block:: sh
      
      $ mv /path/to/omeka/archive/ /path/to/omeka/files/

*********************
Logging and Debugging
*********************

Developers of both themes and plugins will need to be aware of the following changes in Omeka's ``.htaccess`` file and ``config.ini`` file in ``application/config``. Compare your existing files to the new ``.htaccess.changeme`` and ``config.ini.changeme`` files

* ``.htaccess`` now includes an environment variable for development: ``# SetEnv APPLICATION_ENV development``
* ``config.ini`` now includes a setting for the minimal level of error logging. The default level is WARN. DEBUG is the
  lowest level of priority, and will show all messages. :ref:`flog` allows you to set your a priority,
  and the setting in ``config.ini`` must be set appropriately for the messages to be saved.

  .. code-block:: ini
  
      ; log.priority
      ; The minimum priority level of messages that should be logged.
      ; default: Zend_Log::WARN (Logs warnings and above)
      log.priority = Zend_Log::DEBUG
  
  .. note::

     :ref:`fdebug` uses DEBUG priority, so to see messages logged by that function you must set the log priorty
     to DEBUG in ``config.ini``. 

*****************
Upgrading Plugins
*****************

As you look through the lists of typical tasks below, you might also want to consult :ref:`bestPracticesPlugins`

Typical tasks you will need to do to upgrade your plugins for Omeka 2.0 are:

* Change the classes your controllers and models extend from.

  * Omeka_Controller_Action becomes :php:class:`Omeka_Controller_AbstractActionController` 
  * Omeka_Record becomes :php:class:`Omeka_Record_AbstractRecord`

* Update any helper functions you use in hooks for filters.
* Change your hook callbacks to have an array passed in. Typically, the expected variable name passed in in version 
  1.5 (e.g. ``$user``) becomes the key for the corresponding data in the array, e.g. ``$user = $args['user'];``.
  See `Updating Plugins for 2.0: Hooks and Filters <http://omeka.org/codex/Updating_Plugins_For_2.0#Hooks_and_Filters>`_ 
* Update any filters you use. The third argument must now be an array to fit with the standard above.
* Change the helper functions used in the views
  * All functions of the form ``loop_{record type}``, like ``loop_items()``, become ``loop("{record type}")``
* Change usage of functions that previously echoed content. For example, ``<?php head(); ?>`` should now
  be ``<?php echo head(); ?>``.

Database
========

Record classes
--------------

* The abstract class records extend from is now :php:class:`Omeka_Record_AbstractRecord`, not ``Omeka_Record``
* The following callbacks have been **removed**, along with their associated plugin hooks:

  * ``beforeSaveForm``
  * ``afterSaveForm``
  * ``beforeInsert``
  * ``afterInsert``
  * ``beforeUpdate``
  * ``afterUpdate``
  * ``beforeValidate``
  * ``afterValidate``

  A boolean `insert` argument for the ``beforeSave`` and ``afterSave`` callbacks replaces the insert/update hooks.
* The ``saveForm`` and ``forceSave`` methods are **removed**. Use :php:meth:`Omeka_Record_AbstractRecord::save` instead.

Table classes
-------------

* SQL aliases are no longer the initials of the underlying table, they are the full table name (without the prefix).
  For example, the Items table alias was ``i`` in Omeka 1.x, but it is now ``items``. You can call
  :php:meth:`Omeka_Db_Table::getTableAlias` to get the alias.
* Table classes can now optionally use the naming pattern ``Table_{Record}`` instead of ``{Record}Table``. Omeka's
  built-in tables use this new naming scheme.

Built-in records
----------------

* The ``Entity``, ``EntitiesRelations``, and ``EntityRelationships`` models, and their underlying tables are
  **removed**. Any code relying on them must be changed or removed.

  * :php:class:`User` now directly stores the name and email data for users that was previously in the ``Entity``.

Built-in mixins
---------------

* All mixins now have a prefix of ``Mixin_`` on their class name, and have a new naming convention:

  * ``Ownable`` is now :php:class:`Mixin_Owner`.
  * ``Taggable`` is now :php:class:`Mixin_Tag`.
  * ``ActsAsElementText`` is now :php:class:`Mixin_ElementText`.
  * ``PublicFeatured`` is now :php:class:`Mixin_PublicFeatured`.

ACL and Permissions
===================

* ``Omeka_Acl`` is **removed**. All references to ``Omeka_Acl`` should be to ``Zend_Acl`` instead.

  * ``loadRoleList``, ``loadResourceList``, and ``loadAllowList`` were Omeka-specific methods, and are now gone.
    Now, just directly make individual calls to ``addRole()``, ``addResource()``, and ``allow()``. You no longer
    need to use ``loadResourceList()`` to define the privileges for each resource.
  * ``checkUserPermission`` is also gone. Use ``isAllowed`` instead::

        $acl->isAllowed(current_user(), 'Resource', 'privilege');

Controllers
===========

* Many methods that were previously directly called on a Controller are now controller helpers instead.

  * The database wrapper methods ``findById()``, ``getTable('TableName')``, ``getDb()`` are **removed** in favor of
    the Db helper::

        // old: $record = $this->findById();
        $record = $this->_helper->db->findById();

        // old: $element = $this->getTable('Element')->find($elementId);
        $element = $this->_helper->db->getTable('Element')->find($elementId);

        // old: $db = $this->getDb();
        $db = $this->_helper->db->getDb();
  * The Db helper is also now used to set the default model name. The ``_modelClass`` property is **removed** in
    favor of ``setDefaultModelName`` from the Db helper::

        // 1.x
        public function init() 
        {
            $this->_modelClass = 'MyModel';
        }
        
        // 2.0
        public function init() 
        {
            $this->_helper->db->setDefaultModelName('MyModel');
        }

  * The ``flash``, ``flashSuccess``, and ``flashError`` methods are **removed** in favor of the FlashMessenger helper::

        $this->_helper->flashMessenger('A neutral message');
        
        $this->_helper->flashMessenger('A success message!', 'success');

        $this->_helper->flashMessenger('An error message.', 'error');

Omeka_Context
=============

* ``Omeka_Context`` is **removed**. Resources are instead available directly through ``Zend_Registry`` or through
  the bootstrap object::

      $acl = Zend_Registry::get('bootstrap')->getResource('Acl');

Views
=====

Admin Views
-----------

* Many new CSS classes are available and should be used to ensure a consistent look and feel across Omeka plugins.
  It will be helpful to become familiar with them. For example, this is the new code structure to use if you need
  to create inputs yourself:  

  .. code-block:: html

      <div class="field">
           <div class="two columns alpha">
               <label for="some_input" class="required">Some Input Label</label>
           </div>
           <div class="inputs five columns omega">
               <input type="text" name="some_input">
           </div>
       </div>

* Admin theme now displays an ``<h1>`` with the title you set for the page. You can remove those from your admin views. 
* Use new save panel features. For ease of use in the most common cases, the :php:class:`Omeka_Form_Admin` is available.
 
***************
Updating Themes
***************

The number of global functions has been cut nearly in half in Omeka 2.0. This will require many changes to your themes,
but will also make the patterns of usage much easier to follow and much more consistent.

Here are a few of the basic tasks for upgrading.

* Change the various metadata-retrieval functions for different record types (e.g., ``item()``, ``collection()``, etc)
  to the generalized :ref:`fmetadata` function.
* Change the loop structure for the various record types (e.g., ``loop_items()``, ``loop_collections``, etc) to the
  generalized :ref:`floop` function. Note that the structure changes from::

      while(loop_items()):

  to::

      foreach(loop('items') as $item):

* Use :php:func:`get_records` when getting sets of any record within a theme. ``get_items``, ``get_tags``, and
  ``get_collections`` are all replaced by ``get_records``.
* Change other global functions that have changed. There is `a complete list of old and new function names on our
  wiki <http://omeka.org/codex/Updating_Plugins_For_2.0#Function_Replacements>`_.  
* Update calls to hooks and filters (wherever you use :ref:`ffirepluginhook` and :ref:`fapplyfilters`). Typically,
  the expected variable name passed in in version 1.5 (e.g. ``$user``) becomes the key for the corresponding data in
  the array, e.g. ``$user = $args['user'];`` See
  `Updating Plugins for 2.0: Hooks and Filters <http://omeka.org/codex/Updating_Plugins_For_2.0#Hooks_and_Filters>`_
