-----------------------------------------
Omeka_Controller_AbstractActionController
-----------------------------------------

.. php:class:: Omeka_Controller_AbstractActionController

    Package: Controller

    Base class for Omeka controllers.
    
    Provides basic create, read, update, and delete (CRUD) operations.

    .. php:attr:: _browseRecordsPerPage
    
        The number of records to browse per page.
        
        If this is left null, then results will not paginate. This is partiallybecause not every controller will want to
        paginate records and also toavoid BC breaks for plugins.

    .. php:method:: __construct(Zend_Controller_Request_Abstract $request, Zend_Controller_Response_Abstract $response, $invokeArgs = Array)
    
        Base controller constructor.
        
        Does the following things:
        
        	               
        
        .. raw:: html
        
        <ul>
        	                 <li>Aliases the redirector helper to clean up the syntax</li>
        	                 <li>Sets the table object automatically if given the class of the model 
        	               to use for CRUD.</li>
        	                 <li>Sets all the built-in action contexts for the CRUD actions.</li>
        	                </ul>
        
        
        Instead of overriding this constructor, controller subclasses shouldimplement the init() method for initial setup.
        
        :param Zend_Controller_Request_Abstract $request: 
        :param Zend_Controller_Response_Abstract $response: 
        :param unknown $invokeArgs:

    .. php:method:: indexAction()
    
        Forward to the 'browse' action

    .. php:method:: browseAction()
    
        Retrieve and render a set of records for the controller's model.
        
        Using this action requires some setup:
        
        	               
        
        .. raw:: html
        
        <ul>
        	                 <li>In your controller's <code>init()</code>, set the default model name: 
        	                   <code>$this->_helper->db->setDefaultModelName('YourRecord');</code></li>
        	                 <li>In your controller, set the records per page and return them using: 
        	                   <code>protected function _getBrowseRecordsPerPage()</code></li>
        	                 <li>In your table record, filter the select object using the provided 
        	                   parameters using: 
        	                   <code>public function applySearchFilters($select, $params)</code></li>
        	                </ul>

    .. php:method:: showAction()
    
        Retrieve a single record and render it.
        
        Every request to this action must pass a record ID in the 'id' parameter.

    .. php:method:: addAction()
    
        Add an instance of a record to the database.
        
        This behaves differently based on the contents of the $_POST superglobal.If the $_POST is empty or invalid, it will
        render the form used for dataentry. Otherwise, if the $_POST exists and is valid, it will save the newrecord and
        redirect to the 'browse' action.

    .. php:method:: editAction()
    
        Similar to 'add' action, except this requires a pre-existing record.
        
        Every request to this action must pass a record ID in the 'id' parameter.

    .. php:method:: deleteConfirmAction()
    
        Ask for user confirmation before deleting a record.

    .. php:method:: deleteAction()
    
        Delete a record from the database.
        
        Every request to this action must pass a record ID in the 'id' parameter.

    .. php:method:: getCurrentUser()
    
        Return the record for the current user.
        
        :returns: User|bool User object if a user is logged in, false otherwise.

    .. php:method:: _getBrowseRecordsPerPage()
    
        Return the number of records to display per page.
        
        By default this will return null, disabling pagination. This can beoverridden in subclasses by redefining this
        method.
        
        :returns: integer|null

    .. php:method:: _getAddSuccessMessage(Omeka_Record_AbstractRecord $record)
    
        Return the success message for adding a record.
        
        Default is empty string. Subclasses should override it.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: string

    .. php:method:: _getEditSuccessMessage(Omeka_Record_AbstractRecord $record)
    
        Return the success message for editing a record.
        
        Default is empty string. Subclasses should override it.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: string

    .. php:method:: _getDeleteSuccessMessage(Omeka_Record_AbstractRecord $record)
    
        Return the success message for deleting a record.
        
        Default is empty string. Subclasses should override it.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: string

    .. php:method:: _getDeleteConfirmMessage(Omeka_Record_AbstractRecord $record)
    
        Return the delete confirm message for deleting a record.
        
        :param Omeka_Record_AbstractRecord $record: 
        :returns: string

    .. php:method:: _redirectAfterAdd(Omeka_Record_AbstractRecord $record)
    
        Redirect to another page after a record is successfully added.
        
        The default is to reidrect to this controller's browse page.
        
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: _redirectAfterEdit(Omeka_Record_AbstractRecord $record)
    
        Redirect to another page after a record is successfully edited.
        
        The default is to redirect to this record's show page.
        
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: _redirectAfterDelete(Omeka_Record_AbstractRecord $record)
    
        Redirect to another page after a record is successfully deleted.
        
        The default is to redirect to this controller's browse page.
        
        :param Omeka_Record_AbstractRecord $record:

    .. php:method:: _setActionContexts()
    
        Augment Zend's default action contexts.
        
        Passes Omeka's default additional contexts through the
        'define_action_contexts' filter to allow plugins to add contexts.

    .. php:method:: _getDeleteForm()
    
        Get the form used for confirming deletions.
        
        :returns: Zend_Form