.. understandingomekarecordrecordabstract.

#########################################
Understanding Omeka_Record_AbstractRecord
#########################################


:php:class:`Omeka_Plugin_AbstractRecord` is extended to create the models for Omeka and its plugins. It corresponds to a database table, with each row representing an individual record. Table columns correspond to public properties of the class.

.. code-block:: php

    class MyThing extends Omeka_Plugin_AbstractRecord
    {
        /**
        * text Text for the MyThing
        */
        
        public $text;
    
    }

Note that an `$id` property is inherited from `Omeka_Plugin_AbstractRecord`.

To create the database table for a plugin, use Omeka's `install` hook. It will inflect the classes name to make it plural and underscored. For example, a model called `MyThing` will have a table called `my_things`.

For example this code in a plugin's `install` hook will create the table for the above model.

.. code-block:: php

    public function hookInstall() {
        $db = $this->_db;
        $sql = "
        CREATE TABLE IF NOT EXISTS `$db->MyThing` (
          `id` int(10) unsigned NOT NULL AUTO_INCREMENT,
          `text` text NOT NULL,
          . . . 
          ) ENGINE=InnoDB  DEFAULT CHARSET=utf8 COLLATE=utf8_unicode_ci";
        $db->query($sql);
    }

The abstract record contains callback functions creating, reading, updating, and deleting records, both before and after those actions. These are helpful if any automatic processing should be done during those operations.

For example, to append a message to text as the record is saved, override the `beforeSave()` callback.

.. code-block:: php

    protected function beforeSave()
    {
        // only append upon insert
        if (! $this->exists()) {
            $this->text = $this->text . "Hello!";
        }
    }

The `_validate()` function can similarly be overridden to add custom validation code for the record.

