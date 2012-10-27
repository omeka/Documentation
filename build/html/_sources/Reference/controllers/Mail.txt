-----------------------------------
Omeka_Controller_Action_Helper_Mail
-----------------------------------

.. php:class:: Omeka_Controller_Action_Helper_Mail

    Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

    Action helper for sending email.

    .. php:attr:: _view
    


    .. php:attr:: _subject
    
        Subject of the email.

    .. php:attr:: _subjectPrefix
    
        Prefix (prepended to the subject).

    .. php:method:: __construct(Zend_View $view)
    
        :param Zend_View $view: View to render as the message body.

    .. php:method:: __call(string $method, array $args)
    
        Delegate to the Zend_Mail instance.
        
        :param string $method: Method called.
        :param array $args: Arguments to method.

    .. php:method:: setSubjectPrefix(string $prefix)
    
        Set the prefix for the subject header.  Typically takes the form "[Site Name] ".
        
        :param string $prefix: Subject prefix.

    .. php:method:: setSubject(string $subject)
    
        Set the subject of the email.
        
        :param string $subject: Email subject.

    .. php:method:: setBodyFromView(string $viewScript, boolean $html = )
    
        Render the given view and use it as the body of the email.
        
        :param string $viewScript: View script path.
        :param boolean $html: Whether or not the assigned view script will render as HTML.  Defaults to false.

    .. php:method:: send(Zend_Mail_Transport_Abstract $transport)
    
        Send the email.
        
        :param Zend_Mail_Transport_Abstract $transport: Optional defaults to null.