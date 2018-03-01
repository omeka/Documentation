-----------------------------------
Omeka_Controller_Action_Helper_Mail
-----------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_Mail

extends :php:class:`Zend_Controller_Action_Helper_Abstract`

    Action helper for sending email.

    .. php:method:: __construct(Zend_View $view)

        :type $view: Zend_View
        :param $view: View to render as the message body.

    .. php:method:: __call($method, $args)

        Delegate to the Zend_Mail instance.

        :type $method: string
        :param $method: Method called.
        :type $args: array
        :param $args: Arguments to method.

    .. php:method:: setSubjectPrefix($prefix)

        Set the prefix for the subject header.  Typically takes the form "[Site
        Name] ".

        :type $prefix: string
        :param $prefix: Subject prefix.

    .. php:method:: setSubject($subject)

        Set the subject of the email.

        :type $subject: string
        :param $subject: Email subject.

    .. php:method:: setBodyFromView($viewScript, $html = false)

        Render the given view and use it as the body of the email.

        :type $viewScript: string
        :param $viewScript: View script path.
        :type $html: bool
        :param $html: Whether or not the assigned view script will render as HTML.  Defaults to false.

    .. php:method:: send($transport = null)

        Send the email.

        :type $transport: Zend_Mail_Transport_Abstract
        :param $transport: Optional defaults to null.
