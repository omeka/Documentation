----------------------
Omeka_Test_Helper_Mail
----------------------

Package: :doc:`Test\\Helper </Reference/packages/Test/Helper/index>`

.. php:class:: Omeka_Test_Helper_Mail

    Encapsulates testing functionality for email.

    .. php:method:: __construct($path)

        :type $path: string
        :param $path: Real path to the mail storage directory.

    .. php:method:: factory()

        Configure an instance of the Mail helper using the registered test_config.

        :returns: Omeka_Test_Helper_Mail

    .. php:method:: _getIterator()

        Get an iterator over the fakemail directory.

        :returns: DirectoryIterator

    .. php:method:: _isMailFile(SplFileInfo $file)

        Check if a directory entry is a mail message file.

        :type $file: SplFileInfo
        :param $file:
        :returns: boolean

    .. php:method:: getMailText($index = 0)

        Return the text of the n'th email that was sent during the test.

        Note that this will not return correct results if reset() was not invoked
        between test runs.

        :type $index: integer
        :param $index:
        :returns: string

    .. php:method:: count()

        The number of mails that have been sent.
