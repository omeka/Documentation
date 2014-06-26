---------------------------
Omeka_Validate_Confirmation
---------------------------

Package: :doc:`Validate </Reference/packages/Validate/index>`

.. php:class:: Omeka_Validate_Confirmation

extends :php:class:`Zend_Validate_Abstract`

    Adapted from Zend Framework documentation on custom validators.

    .. php:const:: NOT_MATCH

        Error message for non-matching confirmation.

    .. php:attr:: _field

        protected string

        Field needing confirmation.

    .. php:attr:: _messageTemplates

        protected array

        Error messages.

    .. php:attr:: _messageVariables

        protected array

        Error message replace variables.

    .. php:method:: __construct($field)

        Sets validator options

        :param $field:

    .. php:method:: isValid($value, $context = null)

        Check that the value is valid.

        :type $value: string
        :param $value:
        :type $context: string|array
        :param $context:
        :returns: boolean

    .. php:method:: getField()

        Get the name of the field that needs confirmation.

        :returns: string

    .. php:method:: setField($field)

        Set the name of the field that needs confirmation.

        :type $field: string
        :param $field:
        :returns: void
