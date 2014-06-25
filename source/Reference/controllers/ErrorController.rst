---------------
ErrorController
---------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: ErrorController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:method:: errorAction()

    .. php:method:: _getException()

    .. php:method:: notFoundAction()

        Generic action to render a 404 page.

        :returns: void

    .. php:method:: forbiddenAction()

    .. php:method:: methodNotAllowedAction()

    .. php:method:: logException($e, $priority)

        :param $e:
        :param $priority:

    .. php:method:: is404(Exception $e, $handler)

        Check to see whether the error qualifies as a 404 error

        :type $e: Exception
        :param $e:
        :param $handler:
        :returns: boolean

    .. php:method:: is403(Exception $e)

        :type $e: Exception
        :param $e:

    .. php:method:: renderException(Exception $e)

        :type $e: Exception
        :param $e:

    .. php:method:: isInDebugMode()
