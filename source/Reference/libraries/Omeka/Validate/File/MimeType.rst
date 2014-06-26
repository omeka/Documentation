----------------------------
Omeka_Validate_File_MimeType
----------------------------

Package: :doc:`Validate </Reference/packages/Validate/index>`

.. php:class:: Omeka_Validate_File_MimeType

extends :php:class:`Zend_Validate_Abstract`

    Validates files against a MIME type whitelist.

    .. php:attr:: _messageTemplates

        protected array

    .. php:attr:: _messageVariables

        protected array

    .. php:attr:: _customWhitelist

        protected string

    .. php:attr:: _file

        protected string

    .. php:attr:: _mimeType

        protected string

    .. php:method:: __construct()

        Construct the validator object.

    .. php:method:: isValid($file)

        Vaidate the file MIME type.

        :type $file: string
        :param $file:
        :returns: bool
