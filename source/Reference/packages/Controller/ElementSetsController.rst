---------------------
ElementSetsController
---------------------

.. php:class:: ElementSetsController

    Package: :doc:`/Reference/packages/Controller/index`

    .. php:method:: init()

    .. php:method:: _getDeleteConfirmMessage($record)
    
        :param unknown $record:

    .. php:method:: addAction()
    
        Can't add element sets via the admin interface, so disable these
        actions from being POST'ed to.
        
        :returns: void

    .. php:method:: editAction()

    .. php:method:: _redirectAfterEdit($record)
    
        :param unknown $record: