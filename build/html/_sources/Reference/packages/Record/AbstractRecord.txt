---------------------------
Omeka_Record_AbstractRecord
---------------------------

.. php:class:: Omeka_Record_AbstractRecord

    Package: :doc:`Record </Reference/packages/Record/index>`

    A base class for domain objects, inspired by, though not strictly adherent 
    to, the ActiveRecord pattern.

    .. php:attr:: id
    
        Unique ID for the record.
        
        All implementations of Omeka_Record_AbstractRecord must have a table containing an 'id' column, preferably as the
        primary key.

    .. php:attr:: _errors
    
        Any errors raised during the validation process.

    .. php:attr:: _cache
    
        An in-memory cache for related objects that have been retrieved
        via the magic __get() syntax.

    .. php:attr:: _mixins
    
        Set of Omeka_Record_Mixin_AbstractMixin objects that are designed to 
        extend the behavior of Omeka_Record_AbstractRecord implementations.
        
        Examples include {@link Taggable}, {@link Relatable},{@link ActsAsElementText}, etc.

    .. php:attr:: _db
    


    .. php:attr:: _related
    
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
    
        Storage for the POST data when handling a form.

    .. php:attr:: _locked
    
        Whether or not the record is locked.
        Locked records cannot be saved.

    .. php:attr:: _eventCallbacks
    
        List of built in callback methods.

    .. php:attr:: _pluginBroker
    


    .. php:method:: __construct(Omeka_Db|null $db)
    
        :param Omeka_Db|null $db: (optional) Defaults to the Omeka_Db instance from the bootstrap.

    .. php:method:: construct()
    
        Subclass constructor behavior.
        
        Subclasses of Omeka_Record_AbstractRecord can override this function toadd behavior to the constructor without
        overriding __construct.
        
        :returns: void

    .. php:method:: __destruct()
    
        Unsets mixins, which contain circular references, upon record destruction
        
        IMPORTANT: Solves a memory leak when retrieving/saving records.
        
        Required because PHP 5.2 does not do garbage collection on circular references.

    .. php:method:: __get(string $prop)
    
        Retrieve database records that are associated with the current one.
        
        :param string $prop: Related data to retrieve.
        :returns: mixed

    .. php:method:: __call(string $m, array $a)
    
        Delegate unknown method calls to Omeka_Record_Mixin_AbstractMixin 
        instances.
        
        :param string $m: Method name.
        :param array $a: Method arguments.
        :returns: mixed

    .. php:method:: _initializeMixins()
    
        Initialize the mixins for a record.
        
        Any Omeka_Record_AbstractRecord subclass that uses mixins shouldinitialize them here, since this is called on
        construction and whenmixins need to be reinitialized.

    .. php:method:: delegateToMixins(string $method, array $args = Array, boolean $all = )
    
        Delegate to the given method in one or more mixin instances.
        
        :param string $method: 
        :param array $args: 
        :param boolean $all: (optional) Whether or not to call the same method on every mixin instance that has that method.  Defaults to false.
        :returns: mixed If $all is false, the return value from the invoked method. Otherwise there is no return value.

    .. php:method:: runCallbacks($event)
    
        Invoke all callbacks associated with a specific record event.
        
        Callbacks execute in the following order:- Omeka_Record_AbstractRecord hooks like
        Omeka_Record_AbstractRecord::afterDelete()- Record mixin hooks like Taggable::afterSave()- Generic record plugin
        hooks like 'before_delete_record'- Specific record plugin hooks like 'before_delete_item'
        
        :param unknown $event: 
        :returns: void

    .. php:method:: _addToCache(mixed $value, string $key)
    
        Add a value to the record-specific cache.
        
        :param mixed $value: 
        :param string $key: 
        :returns: void

    .. php:method:: _getCached(string $name)
    
        Get a value from the record-specific cache.
        
        :param string $name: 
        :returns: mixed

    .. php:method:: getProperty(string $property)
    
        Get a property about the record for display purposes.
        
        :param string $property: Property to get. Always lowercase.
        :returns: mixed

    .. php:method:: exists()
    
        Determine whether or not this record is persistent in the database.
        
        For simplicity, non-persistent records are indicated by the lack of avalue for the 'id' column.
        
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

    .. php:method:: addError(string|null $field, string $msg)
    
        Add a validation error for a specific field.
        
        Currently limited to a single error per field, so multiple error messagesmust be concatenated together.
        
        :param string|null $field: Name of the field.  This can be null to indicate a general error not associated with a specific field.
        :param string $msg: The error message.
        :returns: void

    .. php:method:: addErrorsFrom(Omeka_Record_AbstractRecord $record)
    
        Combine errors from a different Omeka_Record_AbstractRecord instance with 
        the errors already on this record.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: void

    .. php:method:: lock()
    
        Prevent a record from being modified.
        
        Can be used to prevent accidentally saving/deleting a record if its state maychange but saving would be undesirable,
        such as modifying a record fordisplay purposes.
        
        :returns: void

    .. php:method:: getTable($class)
    
        Retrieve the Omeka_Db_Table instance associated with this record, or 
        with that of any given record class.
        
        :param unknown $class: 
        :returns: Omeka_Db_Table

    .. php:method:: getDb()
    
        Retrieve the Omeka_Db instance associated with this record.
        
        :returns: Omeka_Db

    .. php:method:: toArray()
    
        Retrieve an associative array of all the record's columns and their 
        values.
        
        :returns: array

    .. php:method:: save(boolean $throwIfInvalid = 1)
    
        Save the record.
        
        :param boolean $throwIfInvalid: 
        :returns: boolean Whether the save was successful.

    .. php:method:: __clone()
    
        Clone the record.
        
        Unsets the ID so the cloned record can be saved on its own.

    .. php:method:: delete()
    
        Delete the record.
        
        :returns: void

    .. php:method:: _delete()
    
        Template method for defining record deletion logic.
        
        Subclasses can override this method to define additional logic for deletingrecords.  Note that this is different
        from both the beforeDelete() andafterDelete() hooks in that it executes after beforeDelete(), but beforethe record
        is actually deleted.
        
        Common use cases include emulating cascading deletes with otherdatabase rows.
        
        :returns: void

    .. php:method:: beforeSave($args)
    
        Executes before the record is saved.
        
        :param unknown $args:

    .. php:method:: afterSave($args)
    
        Executes after the record is inserted.
        
        :param unknown $args:

    .. php:method:: beforeDelete()
    
        Executes before the record is deleted.

    .. php:method:: afterDelete()
    
        Executes after the record is deleted.

    .. php:method:: setArray(array|Traversable $data)
    
        Set values for the record using an associative array or iterator.
        
        :param array|Traversable $data: 
        :returns: void

    .. php:method:: getPluginBroker()

    .. php:method:: setPluginBroker($broker)
    
        :param unknown $broker:

    .. php:method:: offsetExists(string $name)
    
        Determine whether or not the given field has a value associated with it.
        
        Required by ArrayAccess.
        
        :param string $name: 
        :returns: boolean

    .. php:method:: offsetUnset(string $name)
    
        Unset the given field.
        
        Required by ArrayAccess.
        
        :param string $name: 
        :returns: void

    .. php:method:: offsetGet(string $name)
    
        Retrieve the value of a given field.
        
        Required by ArrayAccess.
        
        :param string $name: 
        :returns: mixed

    .. php:method:: offsetSet(string $name, mixed $value)
    
        Set the value of a given field.
        
        Required by ArrayAccess.
        
        :param string $name: 
        :param mixed $value: 
        :returns: void

    .. php:method:: filterPostData(array $post)
    
        Filter the form input according to some criteria.
        
        Template method should be overridden by subclasses that wish to implementsome sort of filtering criteria.
        
        :param array $post: 
        :returns: array Filtered post data.

    .. php:method:: setPostData(array $post)
    
        Set the POST data to the record.
        
        :param array $post:

    .. php:method:: fieldIsUnique(string $field, mixed $value)
    
        Check uniqueness of one of the record's fields.
        
        :param string $field: 
        :param mixed $value: Optional If null, this will check the value of the record's $field.  Otherwise check the uniqueness of this value for the given field.
        :returns: boolean

    .. php:method:: getRecordUrl(string $action = show)
    
        Get the routing parameters or the URL string to this record.
        
        The record_url() global uses this method to get routing parameters fornon-standard records, e.g. records defined by
        plugins. Subclasses shouldoverride this method if the default route (as defined below) isincorrect.
        
        :param string $action: 
        :returns: string|array A URL string or a routing array.