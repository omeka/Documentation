---------------------------
Omeka_Controller_Router_Api
---------------------------

.. php:class:: Omeka_Controller_Router_Api

    Package: :doc:`Controller\\Router </Reference/packages/Controller/Router/index>`

    Router for the Omeka API.

    .. php:const:: DEFAULT_MODULE
    
    
    
        The default controller name.

    .. php:const:: DEFAULT_CONTROLLER
    
    
    
        The default controller name.

    .. php:attr:: _legalActions
    


    .. php:attr:: _legalParams
    


    .. php:attr:: _legalIndexParams
    


    .. php:method:: getInstance(Zend_Config $config)
    
        :param Zend_Config $config:

    .. php:method:: match(Zend_Controller_Request_Http $request)
    
        Match the user submitted path.
        
        Via Omeka_Application_Resource_Router, this is the only available routefor API requests.
        
        :param Zend_Controller_Request_Http $request: 
        :returns: array|false

    .. php:method:: assemble($data, $reset = , $encode = )
    
        :param unknown $data: 
        :param unknown $reset: 
        :param unknown $encode:

    .. php:method:: _getResource(string $resource, array $apiResources)
    
        Return this route's resource.
        
        :param string $resource: 
        :param array $apiResources: 
        :returns: string

    .. php:method:: _getRecordType(string $resource, array $apiResources)
    
        Return this route's record type.
        
        :param string $resource: 
        :param array $apiResources: 
        :returns: string|null

    .. php:method:: _getModule(string $resource, array $apiResources)
    
        Return this route's module.
        
        :param string $resource: 
        :param array $apiResources: 
        :returns: string

    .. php:method:: _getController(string $resource, array $apiResources)
    
        Return this route's controller.
        
        :param string $resource: 
        :param array $apiResources: 
        :returns: string

    .. php:method:: _getAction(string $method, array $params, string $resource, array $apiResources)
    
        Return this route's action.
        
        :param string $method: 
        :param array $params: 
        :param string $resource: 
        :param array $apiResources: 
        :returns: string

    .. php:method:: _validateParams(string $action, string $resource, array $apiResources)
    
        Validate the GET parameters against the whitelist.
        
        :param string $action: 
        :param string $resource: 
        :param array $apiResources: