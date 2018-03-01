---------------------------------
Omeka_Session_SaveHandler_DbTable
---------------------------------

Package: :doc:`Session </Reference/packages/Session/index>`

.. php:class:: Omeka_Session_SaveHandler_DbTable

extends :php:class:`Zend_Session_SaveHandler_DbTable`

    Wrapper for Zend_Session_SaveHandler_DbTable to hard code the table
    definition. This boosts performance by skipping the DESCRIBE query that
    retrieves this metadata by default.

    Note that this must be updated meticulously after any changes to the sessions table schema.

    .. php:method:: init()

    .. php:method:: write($id, $data)

        Write session data

        :type $id: string
        :param $id:
        :type $data: string
        :param $data:
        :returns: bool
