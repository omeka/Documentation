------------------
SettingsController
------------------

.. php:class:: SettingsController

    Package: :doc:`Controller </Reference/packages/Controller/index>`

    .. php:method:: indexAction()

    .. php:method:: browseAction()

    .. php:method:: editSettingsAction()

    .. php:method:: editSecurityAction()

    .. php:method:: editSearchAction()

    .. php:method:: checkImagemagickAction()
    
        Determine whether or not ImageMagick has been correctly installed and
        configured.
        
        In a few cases, this will indicate failure even though the ImageMagickprogram works properly.  In those cases, users may ignore the results ofthis test.  This is because the 'convert' command may have returned anon-zero status code for some reason.  Keep in mind that a 0 status codealways indicates success.
        
        :returns: boolean True if the command line return status is 0 when attempting to run ImageMagick's convert utility, false otherwise.

    .. php:method:: getFileExtensionWhitelistAction()

    .. php:method:: getFileMimeTypeWhitelistAction()

    .. php:method:: getHtmlPurifierAllowedHtmlElementsAction()

    .. php:method:: getHtmlPurifierAllowedHtmlAttributesAction()