---------------------------
Omeka_Controller_Router_Api
---------------------------

Package: :doc:`Controller\\Router </Reference/packages/Controller/Router/index>`

.. php:class:: Omeka_Controller_Router_Api

extends :php:class:`Zend_Controller_Router_Route_Abstract`

    Router for the Omeka API.

    .. php:const:: DEFAULT_MODULE

        The default controller name.

    .. php:const:: DEFAULT_CONTROLLER

        The default controller name.

    .. php:attr:: _legalActions

        protected All

    .. php:attr:: _legalParams

        protected GET

    .. php:attr:: _legalIndexParams

        protected GET

    .. php:method:: getInstance(Zend_Config $config)

        :type $config: Zend_Config
        :param $config:

    .. php:method:: match($request)

        Match the user submitted path.

        Via Omeka_Application_Resource_Router, this is the only available route
        for API requests.

        :type $request: Zend_Controller_Request_Http
        :param $request:
        :returns: array|false

    .. php:method:: assemble($data = array(), $reset = false, $encode = false)

        :param $data:
        :param $reset:
        :param $encode:

    .. php:method:: _getResource($resource, $apiResources)

        Return this route's resource.

        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
        :returns: string

    .. php:method:: _getRecordType($resource, $apiResources)

        Return this route's record type.

        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
        :returns: string|null

    .. php:method:: _getModule($resource, $apiResources)

        Return this route's module.

        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
        :returns: string

    .. php:method:: _getController($resource, $apiResources)

        Return this route's controller.

        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
        :returns: string

    .. php:method:: _getAction($method, $params, $resource, $apiResources)

        Return this route's action.

        :type $method: string
        :param $method:
        :type $params: array
        :param $params:
        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
        :returns: string

    .. php:method:: _validateParams($action, $resource, $apiResources)

        Validate the GET parameters against the whitelist.

        :type $action: string
        :param $action:
        :type $resource: string
        :param $resource:
        :type $apiResources: array
        :param $apiResources:
