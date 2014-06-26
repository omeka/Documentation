-----------------------------------------
Omeka_Controller_AbstractActionController
-----------------------------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: Omeka_Controller_AbstractActionController

extends :php:class:`Zend_Controller_Action`

    Base class for Omeka controllers.

    Provides basic create, read, update, and delete (CRUD) operations.

    .. php:attr:: _browseRecordsPerPage

        protected string

        The number of records to browse per page.

        If this is left null, then results will not paginate. This is partially
        because not every controller will want to paginate records and also to
        avoid BC breaks for plugins.

    .. php:method:: __construct(Zend_Controller_Request_Abstract $request, Zend_Controller_Response_Abstract $response, $invokeArgs = array())

        Base controller constructor.

        Does the following things:

        - Aliases the redirector helper to clean up the syntax
        - Sets the table object automatically if given the class of the model to
        use for CRUD.
        - Sets all the built-in action contexts for the CRUD actions.

        Instead of overriding this constructor, controller subclasses should
        implement the init() method for initial setup.

        :type $request: Zend_Controller_Request_Abstract
        :param $request: Current request object.
        :type $response: Zend_Controller_Response_Abstract
        :param $response: Response object.
        :type $invokeArgs: array
        :param $invokeArgs: Arguments passed to Zend_Controller_Action.

    .. php:method:: indexAction()

        Forward to the 'browse' action

    .. php:method:: browseAction()

        Retrieve and render a set of records for the controller's model.

        Using this action requires some setup:

        - In your controller's ``init()``, set the default model name
        ``$this->_helper->db->setDefaultModelName('YourRecord');``
        - In your controller, set the records per page and return them using:
        ``protected function _getBrowseRecordsPerPage();``
        - In your table record, filter the select object using the provided
        parameters using: ``public function applySearchFilters($select,
        $params);``

    .. php:method:: showAction()

        Retrieve a single record and render it.

        Every request to this action must pass a record ID in the 'id' parameter.

    .. php:method:: addAction()

        Add an instance of a record to the database.

        This behaves differently based on the contents of the $_POST superglobal.
        If the $_POST is empty or invalid, it will render the form used for data
        entry. Otherwise, if the $_POST exists and is valid, it will save the new
        record and redirect to the 'browse' action.

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

        By default this will return null, disabling pagination. This can be
        overridden in subclasses by redefining this method.

        :returns: integer|null

    .. php:method:: _getAddSuccessMessage($record)

        Return the success message for adding a record.

        Default is empty string. Subclasses should override it.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: string

    .. php:method:: _getEditSuccessMessage($record)

        Return the success message for editing a record.

        Default is empty string. Subclasses should override it.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: string

    .. php:method:: _getDeleteSuccessMessage($record)

        Return the success message for deleting a record.

        Default is empty string. Subclasses should override it.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: string

    .. php:method:: _getDeleteConfirmMessage($record)

        Return the delete confirm message for deleting a record.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
        :returns: string

    .. php:method:: _redirectAfterAdd($record)

        Redirect to another page after a record is successfully added.

        The default is to reidrect to this controller's browse page.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: _redirectAfterEdit($record)

        Redirect to another page after a record is successfully edited.

        The default is to redirect to this record's show page.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: _redirectAfterDelete($record)

        Redirect to another page after a record is successfully deleted.

        The default is to redirect to this controller's browse page.

        :type $record: Omeka_Record_AbstractRecord
        :param $record:

    .. php:method:: _setActionContexts()

        Augment Zend's default action contexts.

        Passes Omeka's default additional contexts through the
        'action_contexts' filter to allow plugins to add contexts.

    .. php:method:: _getDeleteForm()

        Get the form used for confirming deletions.

        :returns: Zend_Form
