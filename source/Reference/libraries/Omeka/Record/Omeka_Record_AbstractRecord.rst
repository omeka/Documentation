---------------------------
Omeka_Record_AbstractRecord
---------------------------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Omeka_Record_AbstractRecord

implements :php:interface:`ArrayAccess`

    A base class for domain objects, inspired by, though not strictly adherent
    to, the ActiveRecord pattern.

    .. php:attr:: id

        integer

        Unique ID for the record.

        All implementations of Omeka_Record_AbstractRecord must have a table
        containing an 'id' column, preferably as the primary key.

    .. php:attr:: _cache

        protected array

        An in-memory cache for related objects that have been retrieved
        via the magic __get() syntax.

    .. php:attr:: _mixins

        protected array

        Set of Omeka_Record_Mixin_AbstractMixin objects that are designed to
        extend the behavior of Omeka_Record_AbstractRecord implementations.

        Examples include {@link Taggable}, {@link Relatable},
        {@link ActsAsElementText}, etc.

    .. php:attr:: _db

        protected Omeka_Db

    .. php:attr:: _related

        protected array

        Key/value pairs indicating aliases for methods that retrieve
        related data objects.
        For example, a subclass might define the following:
        <code>
        protected $_related = array('Sections'=>'loadSections');
        </code>
        This would allow the client to write code like:
        <code>
        $sections = $subclassInstance->Sections;
        </code>
        Which would be equivalent to:
        <code>
        $sections = $subclassInstance->loadSections();
        </code>
        The difference being, the former is cached so as to avoid multiple
        trips to the database.

    .. php:attr:: _postData

        protected ArrayObject

        Storage for the POST data when handling a form.

    .. php:method:: __construct($db = null)

        :type $db: Omeka_Db|null
        :param $db: (optional) Defaults to the Omeka_Db instance from the bootstrap.

    .. php:method:: construct()

        Subclass constructor behavior.

        Subclasses of Omeka_Record_AbstractRecord can override this function to
        add behavior to the constructor without overriding __construct.

        :returns: void

    .. php:method:: __destruct()

        Unsets mixins, which contain circular references, upon record destruction

        IMPORTANT: Solves a memory leak when retrieving/saving records.

        Required because PHP 5.2 does not do garbage collection on circular
        references.

    .. php:method:: __get($prop)

        Retrieve database records that are associated with the current one.

        :type $prop: string
        :param $prop: Related data to retrieve.
        :returns: mixed

    .. php:method:: __call($m, $a)

        Delegate unknown method calls to Omeka_Record_Mixin_AbstractMixin
        instances.

        :type $m: string
        :param $m: Method name.
        :type $a: array
        :param $a: Method arguments.
        :returns: mixed

    .. php:method:: _initializeMixins()

        Initialize the mixins for a record.

        Any Omeka_Record_AbstractRecord subclass that uses mixins should
        initialize them here, since this is called on construction and when mixins
        need to be reinitialized.

    .. php:method:: delegateToMixins($method, $args = array(), $all = false)

        Delegate to the given method in one or more mixin instances.

        :type $method: string
        :param $method:
        :type $args: array
        :param $args:
        :type $all: boolean
        :param $all: (optional) Whether or not to call the same method on every mixin instance that has that method.  Defaults to false.
        :returns: mixed If $all is false, the return value from the invoked method. Otherwise there is no return value.

    .. php:method:: runCallbacks($event, $args = array())

        Invoke all callbacks associated with a specific record event.

        Callbacks execute in the following order:
        - Omeka_Record_AbstractRecord hooks like
        Omeka_Record_AbstractRecord::afterDelete()
        - Record mixin hooks like Taggable::afterSave()
        - Generic record plugin hooks like 'before_delete_record'
        - Specific record plugin hooks like 'before_delete_item'

        :param $event:
        :param $args:

    .. php:method:: _addToCache($value, $key)

        Add a value to the record-specific cache.

        :type $value: mixed
        :param $value:
        :type $key: string
        :param $key:
        :returns: void

    .. php:method:: _getCached($name)

        Get a value from the record-specific cache.

        :type $name: string
        :param $name:
        :returns: mixed

    .. php:method:: getProperty($property)

        Get a property about the record for display purposes.

        :type $property: string
        :param $property: Property to get. Always lowercase.
        :returns: mixed

    .. php:method:: exists()

        Determine whether or not this record is persistent in the database.

        For simplicity, non-persistent records are indicated by the lack of a
        value for the 'id' column.

        :returns: boolean

    .. php:method:: _validate()

        Template method for defining record validation rules.

        Should be overridden by subclasses.

        :returns: void

    .. php:method:: isValid()

        Determine whether or not the record is valid.

        :returns: boolean

    .. php:method:: getErrors()

        Retrieve validation errors associated with this record.

        :returns: Omeka_Validate_Errors

    .. php:method:: hasErrors()

        Determine whether or not this record has any validation errors.

        :returns: boolean

    .. php:method:: addError($field, $msg)

        Add a validation error for a specific field.

        Currently limited to a single error per field, so multiple error messages
        must be concatenated together.

        :type $field: string|null
        :param $field: Name of the field.  This can be null to indicate a general error not associated with a specific field.
        :type $msg: string
        :param $msg: The error message.
        :returns: void

    .. php:method:: addErrorsFrom(Omeka_Record_AbstractRecord $record)

        Combine errors from a different Omeka_Record_AbstractRecord instance with
        the errors already on this record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: void

    .. php:method:: lock()

        Prevent a record from being modified.

        Can be used to prevent accidentally saving/deleting a record if its state
        may change but saving would be undesirable, such as modifying a record for
        display purposes.

        :returns: void

    .. php:method:: getTable($class = null)

        Retrieve the Omeka_Db_Table instance associated with this record, or
        with that of any given record class.

        :param $class:
        :returns: Omeka_Db_Table

    .. php:method:: getDb()

        Retrieve the Omeka_Db instance associated with this record.

        :returns: Omeka_Db

    .. php:method:: toArray()

        Retrieve an associative array of all the record's columns and their
        values.

        :returns: array

    .. php:method:: save($throwIfInvalid = true)

        Save the record.

        :type $throwIfInvalid: boolean
        :param $throwIfInvalid:
        :returns: boolean Whether the save was successful.

    .. php:method:: __clone()

        Clone the record.

        Unsets the ID so the cloned record can be saved on its own.

    .. php:method:: delete()

        Delete the record.

        :returns: void

    .. php:method:: _delete()

        Template method for defining record deletion logic.

        Subclasses can override this method to define additional logic for
        deleting records.  Note that this is different from both the
        beforeDelete() and afterDelete() hooks in that it executes after
        beforeDelete(), but before the record is actually deleted.

        Common use cases include emulating cascading deletes with other database
        rows.

        :returns: void

    .. php:method:: beforeSave($args)

        Executes before the record is saved.

        :param $args:

    .. php:method:: afterSave($args)

        Executes after the record is inserted.

        :param $args:

    .. php:method:: beforeDelete()

        Executes before the record is deleted.

    .. php:method:: afterDelete()

        Executes after the record is deleted.

    .. php:method:: setArray($data)

        Set values for the record using an associative array or iterator.

        :type $data: array|Traversable
        :param $data:
        :returns: void

    .. php:method:: getPluginBroker()

    .. php:method:: setPluginBroker($broker = null)

        :param $broker:

    .. php:method:: offsetExists($name)

        Determine whether or not the given field has a value associated with it.

        Required by ArrayAccess.

        :type $name: string
        :param $name:
        :returns: boolean

    .. php:method:: offsetUnset($name)

        Unset the given field.

        Required by ArrayAccess.

        :type $name: string
        :param $name:
        :returns: void

    .. php:method:: offsetGet($name)

        Retrieve the value of a given field.

        Required by ArrayAccess.

        :type $name: string
        :param $name:
        :returns: mixed

    .. php:method:: offsetSet($name, $value)

        Set the value of a given field.

        Required by ArrayAccess.

        :type $name: string
        :param $name:
        :type $value: mixed
        :param $value:
        :returns: void

    .. php:method:: filterPostData($post)

        Filter the form input according to some criteria.

        Template method should be overridden by subclasses that wish to implement
        some sort of filtering criteria.

        :type $post: array
        :param $post:
        :returns: array Filtered post data.

    .. php:method:: setPostData($post)

        Set the POST data to the record.

        :type $post: array
        :param $post:

    .. php:method:: fieldIsUnique($field, $value = null)

        Check uniqueness of one of the record's fields.

        :type $field: string
        :param $field:
        :type $value: mixed
        :param $value: Optional If null, this will check the value of the record's $field.  Otherwise check the uniqueness of this value for the given field.
        :returns: boolean

    .. php:method:: getRecordUrl($action = 'show')

        Get the routing parameters or the URL string to this record.

        The record_url() global uses this method to get routing parameters for
        non-standard records, e.g. records defined by plugins. Subclasses should
        override this method if the default route (as defined below) is incorrect.

        :type $action: string
        :param $action:
        :returns: string|array A URL string or a routing array.

    .. php:method:: getFile()

        Get a representative file for this record.

        :returns: File|null
