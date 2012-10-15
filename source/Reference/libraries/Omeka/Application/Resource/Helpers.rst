----------------------------------
Omeka_Application_Resource_Helpers
----------------------------------

.. php:class:: Omeka_Application_Resource_Helpers

    Package: Application\Resource

    Initializes controller action helpers.

    .. php:method:: init()

    .. php:method:: _initDbHelper()

    .. php:method:: _initViewRenderer()

    .. php:method:: _initResponseContexts()
    
        Define the custom response format contexts for Omeka.
        
        Plugin writers should use the 'define_response_contexts' filter to modify or expand the list of formats that
        existing controllers may respond to.
        
        
        Example of a definition of a response context through the ZF API:
        
        $contexts->addContext('dc', array('suffix'    => 'dc','headers'   => array('Content-Type' => 'text/xml'),'callbacks'
        => array('init' => 'atBeginningDoThis','post' => 'afterwardsDoThis')));
        
        :returns: void

    .. php:method:: getDefaultResponseContexts()
    
        Returns the default response contexts for Omeka.
        
        :returns: array

    .. php:method:: _initAclHelper()