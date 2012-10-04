------------
Mixin_Search
------------

.. php:class:: Mixin_Search

    Make an Omeka record fulltext searchable.
    
    Any class that extends Omeka_Record_AbstractRecord can be made searchable by pushing an instance of this mixin into Omeka_Record::$_mixins during Omeka_Record::_initializeMixins(). It must be pushed after all mixins that can add search text--for example, after ElementText.
    
    The record type must also be registered using the search_record_types filter in order for the records to be searchable. See self::getSearchRecordTypes().
    
    This mixin leverages the Omeka_Record_AbstractRecord::afterSave() and Omeka_Record_Mixin_AbstractMixin::afterSave() callbacks, so note their order of execution. Records that initialize ActsAsElementText will automatically add their element texts to the search text.

    .. php:attr:: _text
    


    .. php:attr:: _title
    


    .. php:attr:: _public
    


    .. php:method:: __construct($record)
    
        :param unknown $record:

    .. php:method:: addSearchText(string $text)
    
        Add search text to this record.
        
        This method is meant to be called during afterSave().
        
        :param string $text:

    .. php:method:: setSearchTextTitle(string $title)
    
        Add a title to this record.
        
        This method is meant to be called during afterSave().
        
        :param string $title:

    .. php:method:: setSearchTextPrivate()
    
        Mark this record's search text as not public.
        
        This method is meant to be called during afterSave().

    .. php:method:: afterSave($args)
    
        Save the accumulated search text to the database.
        
        :param unknown $args:

    .. php:method:: afterDelete()
    
        Delete this record's search text after it has been deleted.

    .. php:method:: saveSearchText(string $recordType, int $recordId, string $text, string $title, int $public = 1)
    
        Save a search text row.
        
        Call this statically only when necessary. Used primarily when in a record that does not implement Mixin_Search but
        contains text that is needed for another record's search text. For example, when saving a child record that contains
        search text that should be saved to its parent record.
        
        :param string $recordType: 
        :param int $recordId: 
        :param string $text: 
        :param string $title: 
        :param int $public:

    .. php:method:: getSearchRecordTypes()
    
        Get the search record types.
        
        Returns an array containing all record types (i.e. class names) in the application/models directory that should be
        indexed and searchable. These classes must extend Omeka_Record_AbstractRecord and implement this search mixin.
        
        :returns: array