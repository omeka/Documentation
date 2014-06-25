------------------
SettingsController
------------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: SettingsController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:method:: indexAction()

    .. php:method:: browseAction()

    .. php:method:: editSettingsAction()

    .. php:method:: editSecurityAction()

    .. php:method:: editSearchAction()

    .. php:method:: editItemTypeElementsAction()

    .. php:method:: editApiAction()

    .. php:method:: checkImagemagickAction()

        Determine whether or not ImageMagick has been correctly installed and
        configured.

        In a few cases, this will indicate failure even though the ImageMagick
        program works properly.  In those cases, users may ignore the results of
        this test.  This is because the 'convert' command may have returned a
        non-zero status code for some reason.  Keep in mind that a 0 status code
        always indicates success.

        :returns: boolean True if the command line return status is 0 when attempting to run ImageMagick's convert utility, false otherwise.

    .. php:method:: getFileExtensionWhitelistAction()

    .. php:method:: getFileMimeTypeWhitelistAction()

    .. php:method:: getHtmlPurifierAllowedHtmlElementsAction()

    .. php:method:: getHtmlPurifierAllowedHtmlAttributesAction()
