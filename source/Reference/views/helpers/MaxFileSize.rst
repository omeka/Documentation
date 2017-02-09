-----------------------------
Omeka_View_Helper_MaxFileSize
-----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_MaxFileSize

extends :php:class:`Zend_View_Helper_Abstract`

    .. php:attr:: _maxFileSize

        protected string

    .. php:method:: __construct()

        Set the maximum file size.

        The maximum file size is the least of the configurations that affect
        maximum file size.

    .. php:method:: maxFileSize()

        Return the maximum file size.

        :returns: string

    .. php:method:: _parseSize($sizeString)

        Get the size in bytes represented by the given php ini config string

        :type $sizeString: string
        :param $sizeString:
        :returns: int Size in bytes
