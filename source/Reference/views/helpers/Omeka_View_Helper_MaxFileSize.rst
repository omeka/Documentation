-----------------------------
Omeka_View_Helper_MaxFileSize
-----------------------------

Package: :doc:`View\\Helper </Reference/packages/View/Helper/index>`

.. php:class:: Omeka_View_Helper_MaxFileSize

extends :php:class:`Zend_View_Helper_Abstract`

    .. php:attr:: _maxFileSize

        protected Zend_Measure_Binary

    .. php:method:: __construct()

        Set the maximum file size.

        The maximum file size is the least of the configurations that affect
        maximum file size.

    .. php:method:: maxFileSize()

        Return the maximum file size.

        :returns: Zend_Measure_Binary

    .. php:method:: _getSizeMeasure($size)

        Get the binary measurements for file size.

        :type $size: string|int
        :param $size:
        :returns: Zend_Measure_Binary
