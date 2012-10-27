------------
Mixin_Search
------------

.. php:class:: Mixin_Search

    Package: :doc:`Record\\Mixin </Reference/packages/Record/Mixin/index>`

    Make an Omeka record fulltext searchable.
    
    Any class that extends Omeka_Record_AbstractRecord can be made searchable bypushing an instance of this mixin into Omeka_Record::$_mixins duringOmeka_Record::_initializeMixins(). It must be pushed after all mixins thatcan add search text--for example, after ElementText.
    
    The record type must also be registered using the search_record_types filter in order for the records to be searchable.
    
    This mixin leverages the Omeka_Record_AbstractRecord::afterSave() andOmeka_Record_Mixin_AbstractMixin::afterSave() callbacks, so note their orderof execution. Records that initialize ActsAsElementText will automaticallyadd their element texts to the search text.

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
        
        Call this statically only when necessary. Used primarily when in a recordthat does not implement Mixin_Search but
        contains text that is needed foranother record's search text. For example, when saving a child recordthat contains
        search text that should be saved to its parent record.
        
        :param string $recordType: 
        :param int $recordId: 
        :param string $text: 
        :param string $title: 
        :param int $public: