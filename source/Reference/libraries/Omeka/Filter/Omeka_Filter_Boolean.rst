--------------------
Omeka_Filter_Boolean
--------------------

Package: :doc:`Filter </Reference/packages/Filter/index>`

.. php:class:: Omeka_Filter_Boolean

implements :php:interface:`Zend_Filter_Interface`

    A Zend_Filter implementation that converts any boolean value passed to it to
    an integer: 1 or 0.

    .. php:method:: filter($value)

        Filter the value

        :param $value:
        :returns: int 1 or 0
