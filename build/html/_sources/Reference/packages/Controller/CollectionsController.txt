---------------------
CollectionsController
---------------------

.. php:class:: CollectionsController

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    .. php:attr:: contexts
    


    .. php:attr:: _browseRecordsPerPage
    


    .. php:method:: init()

    .. php:method:: browseAction()
    
        The browse collections action.

    .. php:method:: showAction()
    
        The show collection action

    .. php:method:: addAction()
    
        The add collection action

    .. php:method:: editAction()
    
        The edit collection action

    .. php:method:: _getAddSuccessMessage($collection)
    
        :param unknown $collection:

    .. php:method:: _getEditSuccessMessage($collection)
    
        :param unknown $collection:

    .. php:method:: _getDeleteSuccessMessage($collection)
    
        :param unknown $collection:

    .. php:method:: _getDeleteConfirmMessage($collection)
    
        :param unknown $collection:

    .. php:method:: _getElementMetadata($collection, $elementSetName, $elementName)
    
        :param unknown $collection: 
        :param unknown $elementSetName: 
        :param unknown $elementName:

    .. php:method:: _getCollectionElementSets()
    
        Gets the element sets for the 'Collection' record type.
        
        :returns: array The element sets for the 'Collection' record type