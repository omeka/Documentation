---------------
ItemsController
---------------

.. php:class:: ItemsController

    Package: :doc:`/Reference/packages/Controller/index`

    .. php:attr:: contexts
    


    .. php:attr:: _ajaxRequiredActions
    


    .. php:attr:: _methodRequired
    


    .. php:method:: init()

    .. php:method:: preDispatch()

    .. php:method:: advancedSearchAction()
    
        This shows the advanced search form for items by going to the correct URI.
        
        This form can be loaded as a partial by calling items_search_form().
        
        :returns: void

    .. php:method:: _getItemElementSets()

    .. php:method:: editAction()
    
        Adds an additional permissions check to the built-in edit action.

    .. php:method:: _getAddSuccessMessage($record)
    
        :param unknown $record:

    .. php:method:: _getEditSuccessMessage($record)
    
        :param unknown $record:

    .. php:method:: _getDeleteSuccessMessage($record)
    
        :param unknown $record:

    .. php:method:: _getDeleteConfirmMessage($record)
    
        :param unknown $record:

    .. php:method:: addAction()

    .. php:method:: tagsAction()
    
        Finds all tags associated with items (used for tag cloud)
        
        :returns: void

    .. php:method:: browseAction()
    
        Browse the items.  Encompasses search, pagination, and filtering of
        request parameters.  Should perhaps be split into a separate
        mechanism.
        
        :returns: void

    .. php:method:: _getBrowseRecordsPerPage()
    
        Retrieve the number of items to display on any given browse page.
        This can be modified as a query parameter provided that a user is
        actually logged in.
        
        :returns: integer

    .. php:method:: changeTypeAction()
    
        Find or create an item for this mini-form

    .. php:method:: batchEditAction()
    
        Batch editing of Items. If this is an AJAX request, it will
        render the 'batch-edit' as a partial.
        
        :returns: void

    .. php:method:: batchEditSaveAction()
    
        Processes batch edit information. Only accessible via POST.
        
        :returns: void

    .. php:method:: paginationAction()
    
        Goes to results page based off value in text input.