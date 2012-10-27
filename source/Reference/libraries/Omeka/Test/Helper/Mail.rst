----------------------
Omeka_Test_Helper_Mail
----------------------

.. php:class:: Omeka_Test_Helper_Mail

    Package: :doc:`Test\\Helper </Reference/packages/Test/Helper/index>`

    Encapsulates testing functionality for email.

    .. php:attr:: _path
    
        Path to the mail storage directory.

    .. php:method:: __construct(string $path)
    
        :param string $path: Real path to the mail storage directory.

    .. php:method:: factory()
    
        Configure an instance of the Mail helper using the registered test_config.
        
        :returns: Omeka_Test_Helper_Mail

    .. php:method:: _getIterator()
    
        Get an iterator over the fakemail directory.
        
        :returns: DirectoryIterator

    .. php:method:: _isMailFile(SplFileInfo $file)
    
        Check if a directory entry is a mail message file.
        
        :param SplFileInfo $file: 
        :returns: boolean

    .. php:method:: getMailText(integer $index = 0)
    
        Return the text of the n'th email that was sent during the test.
        
        Note that this will not return correct results if reset() was notinvoked between test runs.
        
        :param integer $index: 
        :returns: string

    .. php:method:: count()
    
        The number of mails that have been sent.