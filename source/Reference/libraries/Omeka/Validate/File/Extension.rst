-----------------------------
Omeka_Validate_File_Extension
-----------------------------

Package: :doc:`Validate </Reference/packages/Validate/index>`

.. php:class:: Omeka_Validate_File_Extension

extends :php:class:`Zend_Validate_File_Extension`

    Define custom behavior for the default whitelist file extension validator.

    Baseline behavior of this class is to tweak the default error messages.
    Messages are intentionally as detailed as possible.  Note that it is the responsibility of plugin writers to suppress or replace these messages if necessary for security reasons, e.g. if displaying it to the end user might expose the site to vulnerability probes.

    .. php:attr:: _messageTemplates

        protected array

        Overrides default error message templates.

    .. php:attr:: _targetExtension

        protected string

        The extension of the file being validated

    .. php:method:: __construct($options = null)

        Constructor retrieves the whitelist from the database if no arguments are
        given.

        :type $options: mixed
        :param $options:

    .. php:method:: isValid($value, $file = null)

        Returns true if and only if the fileextension of $value is included in
        the set extension list.

        :type $value: string
        :param $value: Real file to check for extension.
        :type $file: array
        :param $file: File data from Zend_File_Transfer.
        :returns: bool
