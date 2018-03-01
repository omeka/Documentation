--------------------------------------------
Omeka_Controller_Action_Helper_ContextSwitch
--------------------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_ContextSwitch

extends :php:class:`Zend_Controller_Action_Helper_ContextSwitch`

    Extends the default ContextSwitch action helper to enable JSONP.

    .. php:method:: postJsonContext()

        This extends the default ZF JSON serialization to work with JSONP, which
        enables cross-site AJAX using JSON.
