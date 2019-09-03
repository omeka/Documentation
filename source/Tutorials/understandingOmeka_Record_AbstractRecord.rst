.. understandingomekarecordrecordabstract.

#########################################
Understanding Omeka_Record_AbstractRecord
#########################################

:php:class:`Omeka_Record_AbstractRecord` is the heart of the ORM for Omeka. It is an abtract class that is extended to create the models for
Omeka and its plugins. Each class extending ``Omeka_Record_AbstractRecord`` corresponds to a database table, with each row representing an
individual record. Table columns correspond to public properties of the class.

In plugins, it's best practice to include the name of the plugin at the beginning of each model name, to avoid any potential conflicts with
models from the core or other plugins.

Classes extending ``Omeka_Record_AbstractRecord`` are placed in the ``models`` folder of a plugin (or ``application/models`` in the core).
You can choose to keep the model classes all directly under the ``models`` folder or organize them into subfolders. Omeka will work with
either organizational style, but as with all other class files, additional levels of the folder structure must have corresponding underscores
in the class name. For example, a model named ``MyPluginThing`` would be located at ``<plugin folder>/models/MyPluginThing.php``, while one named
``MyPlugin_Thing`` would be located at ``<plugin folder/models/MyPlugin/Thing.php``.

.. code-block:: php

    class MyPluginThing extends Omeka_Record_AbstractRecord
    {
        /**
         * text Text for the Thing
         */
        public $text;
    }

Note that an ``$id`` property is inherited from ``Omeka_Plugin_AbstractRecord``. All Omeka ORM models have an ``id`` property/column
representing the primary key. Tables that would normally have a composite primary key, like "junction" tables representing
many-to-many relationships, must either have a redundant ``id`` column or be managed outside the ORM.

***************
Database tables
***************

The Omeka convention is for table names to be underscore-separated and pluralized (i.e. a ``MyPluginThing`` model will correspond to a table
``my_plugin_things`` in the database). This convention can be overridden if necessary in the corresponding ``Table`` model.  Accessing a model
name as a property (``$db->MyPluginThing``) from the DB object will return the table name for that model, correctly prepended with the user's
configured database prefix. This is the preferred way to get the table name when needed for SQL queries (like a ``CREATE TABLE`` query).

To create the tables in the database table for a plugin, use the :doc:`install hook </Reference/hooks/install>`. The table must contain
a column for each public property of the model, as well as an auto-incrementing ``id`` column as the primary key. For example, this code
in a plugin would create a table for the above model:

.. code-block:: php

    protected $_hooks = array('install' /* ... */);

    /* ... */

    public function hookInstall() {
        $db = $this->_db;
        $sql = "
        CREATE TABLE IF NOT EXISTS `$db->MyPluginThing` (
          `id` int(10) unsigned NOT NULL AUTO_INCREMENT PRIMARY KEY,
          `text` text NOT NULL
          ) ENGINE=InnoDB DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci";
        $db->query($sql);
    }

Other features like additional indexes besides the primary key would be specified in the CREATE TABLE statement when necessary.

Plugins that create tables should drop them in their :doc:`uninstall hook </Reference/hooks/uninstall>`.

********************
Events and callbacks
********************

The abstract record contains callback functions creating, reading, updating, and deleting records, both before and after those actions. These are helpful if any automatic processing should be done during those operations.

For example, to append to the ``text`` column before the record is saved, override the ``beforeSave()`` callback.

.. code-block:: php

    protected function beforeSave()
    {
        // only append upon insert
        if (! $this->exists()) {
            $this->text = $this->text . "Hello!";
        }
    }

The `_validate()` function can similarly be overridden to add custom validation code for the record.

