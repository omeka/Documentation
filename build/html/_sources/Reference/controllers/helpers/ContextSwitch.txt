--------------------------------------------
Omeka_Controller_Action_Helper_ContextSwitch
--------------------------------------------

.. php:class:: Omeka_Controller_Action_Helper_ContextSwitch

    Package: :doc:`/Reference/packages/Controller\ActionHelper/index`

    Extends the default ContextSwitch action helper to enable JSONP.

    .. php:method:: postJsonContext()
    
        This extends the default ZF JSON serialization to work with JSONP, which
        enables cross-site AJAX using JSON.
        
        :returns: void