---------------------------
Omeka_Controller_Plugin_Api
---------------------------

Package: :doc:`Controller\\Plugin </Reference/packages/Controller/Plugin/index>`

.. php:class:: Omeka_Controller_Plugin_Api

extends :php:class:`Zend_Controller_Plugin_Abstract`

    .. php:attr:: _apiResources

        protected The

        Use the "api_resources" filter to add resources, following this format:

        <code>
        // For the path: /api/your_resources/:id
        'your_resources' => array(
        // Module associated with your resource.
        'module' => 'your-plugin-name',
        // Controller associated with your resource.
        'controller' => 'your-resource-controller',
        // Type of record associated with your resource.
        'record_type' => 'YourResourceRecord',
        // List of actions available for your resource.
        'actions' => array(
        'index',  // GET request without ID
        'get',    // GET request with ID
        'post',   // POST request
        'put',    // PUT request (ID is required)
        'delete', // DELETE request (ID is required)
        ),
        // List of GET parameters available for your index action.
        'index_params' => array('foo', 'bar'),
        )
        </code>

        If not given, "module" and "controller" fall back to their defaults,
        "default" and "api". Resources using the default controller MUST include a
        "record_type". Remove "actions" that are not wanted or not implemented.

    .. php:method:: routeStartup(Zend_Controller_Request_Abstract $request)

        Handle API-specific controller logic.

        Via Omeka_Application_Resource_Frontcontroller, this plugin is only
        registered during an API request.

        :type $request: Zend_Controller_Request_Abstract
        :param $request:

    .. php:method:: getApiResources()

        Get the filtered API resources.

        :returns: array
